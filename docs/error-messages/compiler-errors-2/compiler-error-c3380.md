---
title: Error del compilador C3380 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e35c4edaf24aacbd7eb9938a1dea2c470d32caae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062597"
---
# <a name="compiler-error-c3380"></a>Error del compilador C3380

'class': especificador de acceso de ensamblado no válido; solo se permiten 'public' o 'private'

Cuando se aplican a una clase o estructura administrada, las palabras clave [public](../../cpp/public-cpp.md) y [private](../../cpp/private-cpp.md) indican si la clase se expondrá a través de los metadatos del ensamblado. Solo `public` o `private` pueden aplicarse a una clase en un programa compilado con [/clr](../../build/reference/clr-common-language-runtime-compilation.md).

El `ref` y `value` palabras clave, cuando se usa con [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), indican que una clase es administrada (vea [clases y Structs](../../windows/classes-and-structs-cpp-component-extensions.md)).

El ejemplo siguiente genera la advertencia C3380:

```
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
