---
title: Error del compilador C3073 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3073
dev_langs:
- C++
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a46553530d8aaebaf44a71a41203764695b1868d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050806"
---
# <a name="compiler-error-c3073"></a>Error del compilador C3073

'type': clase ref no tiene un constructor de copias definido por el usuario

En un [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) compilación, el compilador no generará un constructor de copias para un tipo de referencia. En cualquier **/CLR** compilación, debe definir su propio constructor de copias para un tipo de referencia si espera que una instancia del tipo que se va a copiar.

Para obtener más información, consulte [semántica de pila de C++ para tipos de referencia](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3073.

```
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```