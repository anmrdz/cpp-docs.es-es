---
title: Compilador advertencia (nivel 4) C4256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4256
dev_langs:
- C++
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6112a541f4bc7efc0ab36feb14f285cf132b08e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075375"
---
# <a name="compiler-warning-level-4-c4256"></a>Advertencia del compilador (nivel 4) C4256

'function': constructor de clase con bases virtuales tiene '...'; las llamadas pueden no ser compatibles con versiones anteriores de Visual C++

Posible incompatibilidad.

Observe el siguiente ejemplo de código. Si la definición del constructor S2:: s2 (int i,...) se ha compilado con una versión del compilador de Visual C++ anteriores a la versión 7, pero el ejemplo siguiente se compila con la versión actual, la llamada al constructor para S3 no funcionaría correctamente debido un caso especial de cambio de convención de llamada. Si ambos se han compilado mediante Visual C++ 6.0, la llamada no funcionaría todo bien, a menos que se pasa ningún parámetro para los puntos suspensivos.

Para corregir esta advertencia,

1. No use el botón de puntos suspensivos en un constructor.

1. Asegúrese de que todos los componentes de su proyecto se compilan con la versión actual (incluidas las bibliotecas que pueden definir o hacer referencia a esta clase), a continuación, deshabilita la advertencia usando la [advertencia](../../preprocessor/warning.md) pragma.

El ejemplo siguiente genera C4256:

```
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```