---
title: Error del compilador C3519 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3519
dev_langs:
- C++
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac9c1bfe01cee659ae8b637df23a86315b5310f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072789"
---
# <a name="compiler-error-c3519"></a>Error del compilador C3519

'parámetro no válido': parámetro no válido para el atributo embedded_idl

Se pasó un parámetro a la `embedded_idl` atributo de [#import](../../preprocessor/hash-import-directive-cpp.md), pero el compilador no reconoce el parámetro.

Los únicos parámetros que se permiten para `embedded_idl` son `emitidl` y `no_emitidl`.

El ejemplo siguiente genera C3519:

```
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```