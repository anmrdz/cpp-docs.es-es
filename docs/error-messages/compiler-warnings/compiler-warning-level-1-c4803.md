---
title: Compilador advertencia (nivel 1) C4803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4ea3eba61df387364b5103de19a28d88fe6e52a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024832"
---
# <a name="compiler-warning-level-1-c4803"></a>Advertencia del compilador (nivel 1) C4803

'method': el método raise tiene una clase de almacenamiento distinta de la del evento, 'event'

Métodos de evento deben tener la misma clase de almacenamiento que la declaración del evento. El compilador ajusta los métodos del evento para que las clases de almacenamiento son los mismos.

Esta advertencia puede producirse si tiene una clase que implementa un evento de una interfaz. El compilador no genera implícitamente un método raise para un evento en una interfaz. Al implementar esa interfaz en una clase, el compilador genera implícitamente un método raise y ese método no será virtual, por lo tanto, la advertencia. Para obtener más información sobre eventos, vea [eventos](../../windows/event-cpp-component-extensions.md).

Consulte [advertencia](../../preprocessor/warning.md) pragma para obtener información sobre cómo desactivar una advertencia.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C4803.

```
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
