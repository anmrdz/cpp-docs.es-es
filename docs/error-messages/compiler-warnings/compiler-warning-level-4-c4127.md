---
title: Del compilador (nivel 4) de la advertencia C4127 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80f831d527e918fce0551f6a1336fd2fe994917d
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161286"
---
# <a name="compiler-warning-level-4-c4127"></a>Advertencia del compilador (nivel 4) C4127

> la expresión condicional es constante

## <a name="remarks"></a>Comentarios

La expresión de control de un **si** instrucción o **mientras** bucle se evalúa como una constante. Debido a su uso idiomático comunes, a partir de Visual Studio 2015 update 3, constantes trivial como 1 o **true** no desencadenan la advertencia, a menos que sean el resultado de una operación en una expresión.

Si la expresión de control de un **mientras** bucle es una constante porque se sale del bucle en el centro, considere reemplazar el **mientras** bucle con un **para** bucle. Se puede omitir la inicialización, la prueba de terminación y el incremento de un **para** bucle, lo que hace que el bucle infinito, al igual que `while(1)`, y puede salir del bucle desde el cuerpo de la **para** instrucción.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra dos maneras C4127 se genera y se muestra cómo usar un bucle evitar la advertencia:

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```