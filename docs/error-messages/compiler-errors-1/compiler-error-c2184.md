---
title: Error del compilador C2184 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2184
dev_langs:
- C++
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c901dbbe97c47afd8096c89f33db6e3e355cba4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050494"
---
# <a name="compiler-error-c2184"></a>Error del compilador C2184

'type': tipo no válido para la expresión __except, debe ser un entero.

Se usó un tipo en una instrucción [__except](../../c-language/try-except-statement-c.md) , pero el tipo no está permitido.

El ejemplo siguiente genera la advertencia C2184:

```
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

Posible resolución:

```
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```