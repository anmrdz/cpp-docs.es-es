---
title: Error del compilador C2498 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2498
dev_langs:
- C++
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fbd946158157f76b2fc9bfe6cbd3ea9086d09ff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115156"
---
# <a name="compiler-error-c2498"></a>Error del compilador C2498

'function': 'novtable' solo se puede aplicar a definiciones o declaraciones de clase

Este error puede deberse al uso `__declspec(novtable)` con una función.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C2498:

```
// C2498.cpp
// compile with: /c
void __declspec(novtable) f() {}   // C2498
class __declspec(novtable) A {};   // OK
```