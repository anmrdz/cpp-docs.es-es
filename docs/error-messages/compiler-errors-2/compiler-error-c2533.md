---
title: Error del compilador C2533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 528b78e71713725907a9f0e2bd06cec1a8c62e67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045411"
---
# <a name="compiler-error-c2533"></a>Error del compilador C2533

'identificador': los constructores no permiten un tipo de valor devuelto

Un constructor no puede tener un tipo de valor devuelto (ni siquiera un tipo de valor devuelto `void`).

Una causa común de este error es la ausencia de un punto y coma entre el final de una definición de clase y la primera implementación de constructor. El compilador ve la clase como una definición del tipo de valor devuelto para la función de constructor y genera C2533.

El ejemplo siguiente genera el error C2533 y muestra cómo corregirlo:

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```