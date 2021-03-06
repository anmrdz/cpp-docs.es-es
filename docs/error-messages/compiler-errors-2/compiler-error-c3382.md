---
title: Error del compilador C3382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6da27531b95950a12cb9aa95e8e89da94c556d2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035970"
---
# <a name="compiler-error-c3382"></a>Error del compilador C3382

'sizeof' no se admite con /clr:safe

El archivo de resultados de una compilación **/clr:safe** es un archivo de seguridad de tipos comprobable y el operador sizeof no se admite porque el valor devuelto del operador sizeof es size_t, cuyo tamaño varía según el sistema operativo.

Para obtener más información, vea

- [sizeof (operador)](../../cpp/sizeof-operator.md)

- [/clr (Compilación de Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Problemas comunes de migración a 64 bits en Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C3382:

```
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```