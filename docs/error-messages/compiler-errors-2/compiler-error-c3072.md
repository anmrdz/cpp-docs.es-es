---
title: Error del compilador C3072 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3072
dev_langs:
- C++
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a36eaaf12cf9f8909455847036f670f6fc0cd40b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047517"
---
# <a name="compiler-error-c3072"></a>Error del compilador C3072

el operador 'operator' no se puede aplicar a una instancia de una clase ref

utiliza el operador unario '`operator` ' para convertir una instancia de una clase ref en un tipo de identificador

Un tipo CLR requiere operadores CLR, no los operadores nativos (o estándares).  Para obtener más información, consulte [operador de referencia de seguimiento](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3072.

```
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```