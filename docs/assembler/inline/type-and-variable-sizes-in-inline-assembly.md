---
title: Tamaño tipos y variables de ensamblado insertado | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- length
- Type
dev_langs:
- C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3defb0b11a55258aa0a7d8c050d5a59bb6b8eb5a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683627"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Tamaño de tipos y variables de ensamblado insertado

**Específicos de Microsoft**

El **longitud**, **tamaño**, y **tipo** operadores tienen un significado limitado en el ensamblado alineado. No se pueden utilizar en absoluto con el operador `DUP` (porque no se puede definir datos con las directivas o los operadores de MASM). No obstante, puede utilizarlos para buscar el tamaño de variables o tipos de C o C++:

- El **longitud** operador puede devolver el número de elementos en una matriz. Devuelve el valor 1 para las variables que no son de matriz.

- El **tamaño** operador puede devolver el tamaño de una variable de C o C++. Tamaño de una variable es el producto de su **longitud** y **tipo**.

- El **tipo** operador puede devolver el tamaño de una variable o un tipo de C o C++. Si la variable es una matriz, **tipo** devuelve el tamaño de un único elemento de la matriz.

Por ejemplo, si el programa tiene un elemento de 8 **int** matriz,

```cpp
int arr[8];
```

las siguientes expresiones de C y ensamblado producen el tamaño de `arr` y sus elementos.

|__asm|C|Tamaño|
|-------------|-------|----------|
|**LONGITUD** arr|`sizeof`(arr)/`sizeof`(arr[0])|8|
|**TAMAÑO** arr|`sizeof`(arr)|32|
|**TIPO** arr|`sizeof`(arr[0])|4|

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Uso del lenguaje de ensamblado en bloques __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>