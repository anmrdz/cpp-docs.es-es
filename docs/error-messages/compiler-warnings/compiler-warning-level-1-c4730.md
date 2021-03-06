---
title: Compilador advertencia (nivel 1) C4730 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d740e1574d4cc538a27471c07795b7c95dd17565
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070462"
---
# <a name="compiler-warning-level-1-c4730"></a>Advertencia del compilador (nivel 1) C4730

'main': mezcla de _m64 y expresiones pueden ocasionar código incorrecto de punto flotante

Una función usa [__m64](../../cpp/m64.md) y **float**/**doble** tipos. Espacio de registro porque los registros MMX y punto flotante comparten el mismo físico (no se puede usar al mismo tiempo) mediante `__m64` y **float**/**doble** tipos en el mismo función puede producir daños en los datos, podría causar una excepción.

Para utilizar sin ningún riesgo `__m64` tipos y tipos de punto flotante en la misma función, cada instrucción que usa uno de los tipos debe estar separado por el **_m_empty** (para MMX) o **_m_femms** (para 3DNow!) intrínseco.

El ejemplo siguiente genera C4730:

```
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```