---
title: Error del compilador C2392 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2392
dev_langs:
- C++
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c45c5b271235e4ada0945a79087186a213c75343
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064274"
---
# <a name="compiler-error-c2392"></a>Error del compilador C2392

'method1': no se admiten los tipos de valores devueltos de covariante administrados o WinRTtypes, en caso contrario 'method2' se reemplazaría

Tipos devueltos de covariante no se permiten para las funciones miembro de Windows en tiempo de ejecución o cuando se compila con la [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) opción.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera el error C2392 y muestra cómo corregirlo:

```
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```