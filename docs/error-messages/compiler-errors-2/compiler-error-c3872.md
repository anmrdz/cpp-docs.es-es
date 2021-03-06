---
title: Error del compilador C3872 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3872
dev_langs:
- C++
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec6450dca0faa86f3cf27452eff6df9851742d4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018839"
---
# <a name="compiler-error-c3872"></a>Error del compilador C3872

'char': este carácter no se permite en un identificador.

El compilador de C++ respeta el estándar de C++11 respecto de los caracteres permitidos en un identificador. Solo se permiten determinados rangos de caracteres y nombres de carácter universal en un identificador. Se aplican restricciones adicionales respecto del carácter inicial de un identificador. Para obtener más información y una lista de caracteres permitidos y rangos de nombre de carácter universal, consulte [Identifiers](../../cpp/identifiers-cpp.md).

El rango de caracteres permitidos en un identificador es menos restrictivo cuando se compila código C++/CLI. Los identificadores del código compilado con /clr deben regirse por el  [Estándar ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

En el siguiente ejemplo se genera el error C3872:

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```