---
title: Error irrecuperable C1070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1070
dev_langs:
- C++
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7e871b69bb189140a4001d574736a255eefaf61
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055629"
---
# <a name="fatal-error-c1070"></a>Error irrecuperable C1070

el par #if/#endif no coincide en el archivo 'filename'

Una directiva `#if`, `#ifdef`, o `#ifndef` no tiene ningún correspondiente `#endif`.

El ejemplo siguiente genera la advertencia C1070:

```
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

Posible solución:

```
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```