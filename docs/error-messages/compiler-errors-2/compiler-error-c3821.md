---
title: Error del compilador C3821 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3821
dev_langs:
- C++
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e1f9a0bbb8eaae6b316b3d00e4201b2b64222ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023038"
---
# <a name="compiler-error-c3821"></a>Error del compilador C3821

'function': función o tipo administrado no se puede usar en una función no administrada

Funciones con ensamblado alineado o [setjmp](../../c-runtime-library/reference/setjmp.md) no puede contener tipos de valor o clases administradas. Para corregir este error, quite el ensamblado en línea y `setjmp` o quite los objetos administrados.

C3821 también puede producirse si intenta utilizar el almacenamiento automático en una función vararg.  Para obtener más información, consulte [listas de argumentos variables (...) (C++ / C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) y [semántica de pila de C++ para tipos de referencia](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera el error C3821.

```
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera el error C3821.

```
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
