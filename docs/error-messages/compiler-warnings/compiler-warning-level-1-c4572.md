---
title: Compilador advertencia (nivel 1) C4572 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4572
dev_langs:
- C++
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b87b3dd4264db9fd7ea3699f342358fa6d4d5aac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076847"
---
# <a name="compiler-warning-level-1-c4572"></a>Advertencia del compilador (nivel 1) C4572

El atributo [ParamArray] está desusado en /clr; use '...' en su lugar

Se ha utilizado un estilo obsoleto para especificar una lista de argumentos de variable. Cuando se compila para CLR, use la sintaxis de puntos suspensivos en lugar de <xref:System.ParamArrayAttribute>. Para obtener más información, consulte [listas de argumentos variables (...) (C++ / C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C4572.

```
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```