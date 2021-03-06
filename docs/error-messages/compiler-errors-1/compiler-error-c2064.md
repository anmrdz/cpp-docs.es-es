---
title: Error del compilador C2064 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2064
dev_langs:
- C++
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7099c8a8371d7a08c95693fffe0d8814303e783e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098117"
---
# <a name="compiler-error-c2064"></a>Error del compilador C2064

el término no se evalúa como una función con N argumentos

Se realiza una llamada a una función a través de una expresión. La expresión no se evalúa como un puntero para una función con el número de argumentos especificado.

En este ejemplo, el código intenta llamar a elementos que no son funciones como funciones. El ejemplo siguiente genera el error C2064:

```
// C2064.cpp
int i, j;
char* p;
void func() {
   j = i();    // C2064, i is not a function
   p();        // C2064, p doesn't point to a function
}
```

Debe llamar a punteros como funciones miembro no estáticas desde el contexto de una instancia de objeto. El ejemplo siguiente genera el error C2064 y muestra cómo corregirlo:

```
// C2064b.cpp
struct C {
   void func1(){}
   void func2(){}
};

typedef void (C::*pFunc)();

int main() {
   C c;
   pFunc funcArray[2] = {&C::func1, &C::func2};
   (funcArray[0])();    // C2064
   (c.*funcArray[0])(); // OK - function called in instance context
}

```

En una clase, los punteros de función miembro también deben indicar el contexto del objeto de llamada. El ejemplo siguiente genera el error C2064 y muestra cómo corregirlo:

```
// C2064d.cpp
// Compile by using: cl /c /W4 C2064d.cpp
struct C {
   typedef void (C::*pFunc)();
   pFunc funcArray[2];
   void func1(){}
   void func2(){}
   C() {
      funcArray[0] = &C::func1;
      funcArray[1] = &C::func2;
   }
   void func3() {
      (funcArray[0])();   // C2064
      (this->*funcArray[0])(); // OK - called in this instance context
   }
};
```