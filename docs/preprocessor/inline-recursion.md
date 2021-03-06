---
title: inline_recursion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a51428d32c1e7e5863e777302c3c55b728ce11f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083066"
---
# <a name="inlinerecursion"></a>inline_recursion
Controla la expansión en línea de llamadas de función directas o mutuamente recursivas.

## <a name="syntax"></a>Sintaxis

```
#pragma inline_recursion( [{on | off}] )
```

## <a name="remarks"></a>Comentarios

Usar esta directiva pragma para controlar funciones marcada como [inline](../cpp/inline-functions-cpp.md) y [__inline](../cpp/inline-functions-cpp.md) o funciones que el compilador expanda automáticamente bajo el `/Ob2` opción. Uso de esta directiva pragma requiere un [/Ob](../build/reference/ob-inline-function-expansion.md) valor de la opción del compilador de 1 o 2. El estado predeterminado de **inline_recursion** está desactivada. Esta pragma tiene efecto en la primera llamada de función después de que se considere la directiva pragma y no afecta a la definición de la función.

El **inline_recursion** pragma controla cómo se expanden las funciones recursivas. Si **inline_recursion** está desactivada y, si una función insertada llama a sí misma (directa o indirectamente), la función es solo una vez expandida. Si **inline_recursion** está activado, la función se expande varias veces hasta que alcanza el valor establecido con el [inline_depth](../preprocessor/inline-depth.md) pragma, el valor predeterminado para las funciones recursivas definido por el `inline_depth` pragma o una capacidad de limitar.

## <a name="see-also"></a>Vea también

[Directivas pragma y la palabra clave __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_depth](../preprocessor/inline-depth.md)<br/>
[/Ob (Expansión de funciones insertadas)](../build/reference/ob-inline-function-expansion.md)