---
title: Error del compilador C2319 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2319
dev_langs:
- C++
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f485d26ac2a05cc91a1c918c63e319e893b8cf95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103157"
---
# <a name="compiler-error-c2319"></a>Error del compilador C2319

'try/catch' debe ir seguido de una instrucción compuesta. Falta '{'

No se encuentra un bloque `try` o `catch` después de la instrucción `try` o `catch` . El bloque debe incluirse entre llaves.

El ejemplo siguiente genera la advertencia C2319:

```
// C2319.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch( C ) ;    // C2319
   // try the following line instead
   // catch( C ) {}
}
```