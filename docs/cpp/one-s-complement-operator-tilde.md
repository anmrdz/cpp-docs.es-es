---
title: 'Una&#39;operador de complemento de s: ~ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- "~"
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42cfc8dd3f94b5b85616297908a73c9a791b730a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111451"
---
# <a name="one39s-complement-operator-"></a>Una&#39;operador de complemento de s: ~

## <a name="syntax"></a>Sintaxis

```
~ cast-expression
```

## <a name="remarks"></a>Comentarios

El operador de complemento de uno (`~`), denominado a veces operador de “complemento bit a bit”, produce un complemento de uno bit a bit de su operando. Es decir, cada bit que es 1 en el operando es 0 en el resultado. Y a la inversa: cada bit que es 0 en el operando es 1 en el resultado. El operando del operador de complemento de uno debe ser de tipo entero.

## <a name="operator-keyword-for-"></a>Palabra clave del operador para ~

El **compl** operador es el equivalente textual de `~`. Hay dos maneras de acceder a la **compl** operador en los programas: incluir el archivo de encabezado `iso646.h`, o compilar con [/Za](../build/reference/za-ze-disable-language-extensions.md).

## <a name="example"></a>Ejemplo

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

En este ejemplo, el nuevo valor asignado a `y` es el complemento de uno del valor sin signo 0xFFFF, or 0x0000.

La promoción de entero se realiza en operandos enteros y el tipo resultante es el tipo al que se promueve el operando. Consulte [conversiones estándar](standard-conversions.md) para obtener más información sobre cómo se realiza la promoción.

## <a name="see-also"></a>Vea también

[Expresiones con operadores unarios](../cpp/expressions-with-unary-operators.md)<br/>
[Operadores integrados de C++, precedencia y asociatividad](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Operadores aritméticos unarios](../c-language/unary-arithmetic-operators.md)