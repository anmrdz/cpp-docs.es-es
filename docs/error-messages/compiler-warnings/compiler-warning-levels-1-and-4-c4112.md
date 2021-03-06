---
title: Del compilador (niveles 1 y 4) de la advertencia C4112 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9015a7ee7a0b71d3c6aafd3e3b32d4ea1b07f108
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110554"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Advertencia del compilador (niveles 1 y 4) C4112

\#requiere que un número entero entre 1 y el número de línea

La directiva [#line](../../preprocessor/hash-line-directive-c-cpp.md) especifica un parámetro entero que está fuera del intervalo permitido.

Si el parámetro especificado es menor que 1, el contador de línea se restablece en 1. Si el parámetro especificado es mayor que *número*, que es el límite definido por el compilador, el contador de línea no se modifica. Esta es una advertencia de nivel 1 con la compatibilidad con ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) y una advertencia de nivel 4 con las extensiones de Microsoft ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

El ejemplo siguiente genera la advertencia C4112:

```
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```