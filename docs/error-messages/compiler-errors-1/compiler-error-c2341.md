---
title: Error del compilador C2341 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adac1e6f6e5f5d58b6091a389537a42f0e496b31
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020204"
---
# <a name="compiler-error-c2341"></a>Error del compilador C2341

'section name': se debe definir el segmento utilizando #pragma data_seg, code_seg o la sección anterior para usar

Un [asignar](../../cpp/allocate.md) instrucción hace referencia a un segmento aún no se han definido por [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), o [sección](../../preprocessor/section.md) pragmas.

El ejemplo siguiente genera C2341:

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Posible resolución:

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```