---
title: Error del compilador C2734 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2734
dev_langs:
- C++
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc3322d97761f1a463426c71bde58de3591ded4a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100713"
---
# <a name="compiler-error-c2734"></a>Error del compilador C2734

'identifier': un objeto const debe inicializarse si no extern

El identificador se declara `const` pero no inicializado o `extern`.

El ejemplo siguiente genera C2734:

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```