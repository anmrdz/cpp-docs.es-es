---
title: Error del compilador C2460 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2d85ffbc7aa799f0688fbb10021a04ef9455ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022626"
---
# <a name="compiler-error-c2460"></a>Error del compilador C2460

'identificador1': utiliza 'identificador2', que se está definiendo

Una clase o estructura (`identifier2`) se declara como un miembro de sí mismo (`identifier1`). No se permiten definiciones recursivas de clases y estructuras.

El ejemplo siguiente genera C2460:

```
// C2460.cpp
class C {
   C aC;    // C2460
};
```

En su lugar, use una referencia de puntero en la clase.

```
// C2460.cpp
class C {
   C * aC;    // OK
};
```