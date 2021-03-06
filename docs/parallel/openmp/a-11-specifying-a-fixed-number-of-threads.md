---
title: A.11 especificar un número fijo de subprocesos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 892140425dc9f7083c606fce3ffe671a107a65ca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422992"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11 Especificar un número fijo de subprocesos

Algunos programas confían en un número fijo, especificado previamente de subprocesos se ejecute correctamente.  Dado que la configuración predeterminada para el ajuste dinámico del número de subprocesos es definido por la implementación, estos programas pueden elegir desactivar la capacidad de subprocesos dinámica y establecer el número de subprocesos de forma explícita para garantizar la portabilidad. El ejemplo siguiente muestra cómo hacer esto con `omp_set_dynamic` ([sección 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) en página 39), y `omp_set_num_threads` ([sección 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) en la página 36):

```
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

En este ejemplo, el programa se ejecutará correctamente solo si se ejecuta por 16 subprocesos. Si la implementación no es capaz de admitir 16 subprocesos, el comportamiento de este ejemplo es definido por la implementación.

Tenga en cuenta que el número de subprocesos que se ejecutan en una región paralela se mantiene constante durante una región paralela, independientemente de los subprocesos dinámicos de configuración. El mecanismo de subprocesos dinámica determina el número de subprocesos que se utilizarán al principio de la región paralela y mantiene constante para la duración de la región.