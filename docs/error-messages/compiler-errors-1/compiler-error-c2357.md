---
title: Error del compilador C2357 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d6468774947ed92630d0e10badc341c5841a5aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025443"
---
# <a name="compiler-error-c2357"></a>Error del compilador C2357

'identifier': debe ser una función de tipo 'type'

El código declara una versión de la `atexit` función que no coincide con la versión declarada internamente por el compilador. Declarar `atexit` como sigue:

```
int __cdecl atexit(void (__cdecl *)());
```

Para obtener más información, consulte [init_seg](../../preprocessor/init-seg.md).

El ejemplo siguiente genera C2357:

```
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```