---
title: Error del compilador C2217 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4eb8b9fcaffa30f3a5ced5362a0f9d54a45f07e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050624"
---
# <a name="compiler-error-c2217"></a>Error del compilador C2217

'atributo1' requiere 'attribute2'

El primer atributo de la función requiere que el segundo atributo.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Posibles causas del error:

1. Interrumpir (`__interrupt`) función declarada como `near`. Interrumpir las funciones deben ser `far`.

1. Interrumpir la función declarada con `__stdcall`, o `__fastcall`. Funciones de interrupción debe usar C++ convenciones de llamada.

## <a name="example"></a>Ejemplo

C2217 también puede producirse si intenta enlazar a un delegado a una función CLR que toma un número variable de argumentos. Si la función también tiene la sobrecarga de matriz param e, use en su lugar. El ejemplo siguiente genera el error C2217.

```
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```