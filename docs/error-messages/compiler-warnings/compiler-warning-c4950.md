---
title: Advertencia del compilador C4950 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4950
dev_langs:
- C++
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 750295da5d2da42ae4c2aac4fbb04dd208a7f32c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072217"
---
# <a name="compiler-warning-c4950"></a>Advertencia del compilador C4950

'type_or_member': marcado como obsoleto

Un miembro o tipo se marcó como obsoleto con la <xref:System.ObsoleteAttribute> atributo.

La advertencia C4950 siempre se emite como un error. Puede desactivar esta advertencia mediante la [advertencia](../../preprocessor/warning.md) directiva pragma o [/wd](../../build/reference/compiler-option-warning-level.md) opción del compilador.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C4950:

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```