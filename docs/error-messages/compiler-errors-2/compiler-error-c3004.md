---
title: Error del compilador C3004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3004
dev_langs:
- C++
helpviewer_keywords:
- C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ccca52b5977c5d709b79dbc6351b5a94605849
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068810"
---
# <a name="compiler-error-c3004"></a>Error del compilador C3004

'clause': cláusula no válida en la directiva 'directive' de OpenMP

Se usó una cláusula de OpenMP en una directiva para la que no está habilitada.

El ejemplo siguiente genera la advertencia C3004:

```
// C3004.c
// compile with: /openmp
int main()
{
   int x, y, z;

   // Shared clause not allowed for 'single' directive.
   #pragma omp single shared(x, y)   // C3004

   x = y;
}
```