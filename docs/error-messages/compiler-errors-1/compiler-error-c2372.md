---
title: Error del compilador C2372 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2372
dev_langs:
- C++
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61407ef7d3c0ca11ac5d95e25cc27c1abc9bf0d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041966"
---
# <a name="compiler-error-c2372"></a>Error del compilador C2372

'identifier': redefinición; diferentes tipos de direccionamiento indirecto

El identificador ya está definido con un tipo derivado diferentes.

El ejemplo siguiente genera la advertencia C2326:

```
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```