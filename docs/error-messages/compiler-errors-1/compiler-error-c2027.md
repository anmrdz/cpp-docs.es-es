---
title: Error del compilador C2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69aae289fbab56cd77e544118909b2d7ef72ae0c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032047"
---
# <a name="compiler-error-c2027"></a>Error del compilador C2027

el uso de un tipo no definido 'type'

No se puede usar un tipo hasta que se define. Para resolver el error, asegúrese de que el tipo se define completamente antes de hacer referencia a ella.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C2027.

```
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

## <a name="example"></a>Ejemplo

Es posible declarar un puntero a un tipo declarado pero no definido.  Pero Visual C++ no permite una referencia a un tipo no definido.

El ejemplo siguiente genera C2027.

```
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```