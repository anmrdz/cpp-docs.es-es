---
title: Del compilador (nivel 4) de la advertencia C4457 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62232a814bed47f8b6a5041d20e6f37776abffe8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093537"
---
# <a name="compiler-warning-level-4-c4457"></a>Compilador advertencia (nivel 4) C4457

> declaración de '*identificador*' oculta el parámetro de función

La declaración de *identificador* en el ámbito local oculta la declaración del parámetro de función con un nombre idéntico. Esta advertencia le permite saber que las referencias a *identificador* en el ámbito local, resolver la versión declarada localmente, no el parámetro, que puede ser o no su intención. Para corregir este problema, se recomienda que proporcionar nombres de variables locales que no entren en conflicto con los nombres de parámetro.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C4457 porque el parámetro `x` y la variable local `x` en `member_fn` tienen los mismos nombres. Para corregir este problema, use nombres diferentes para los parámetros y variables locales.

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
