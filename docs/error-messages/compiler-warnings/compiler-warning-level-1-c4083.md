---
title: Compilador advertencia (nivel 1) C4083 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4083
dev_langs:
- C++
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64e81b6a68a9584e4fb30829e15da6472212ce05
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046373"
---
# <a name="compiler-warning-level-1-c4083"></a>Compilador advertencia (nivel 1) C4083

se esperaba 'token'; se encontró el identificador 'identificador'

Se produce un identificador en el lugar incorrecto en una **#pragma** instrucción.

## <a name="example"></a>Ejemplo

```
// C4083.cpp
// compile with: /W1 /LD
#pragma warning disable:4083    // C4083
#pragma warning(disable:4083)   //correct
```

Compruebe la sintaxis de la [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) directivas.