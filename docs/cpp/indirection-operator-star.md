---
title: 'Operador de direccionamiento indirecto: * | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01ceee27c58dc654b7022d3e9f56129e8914040b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110567"
---
# <a name="indirection-operator-"></a>Operador de direccionamiento indirecto: *

## <a name="syntax"></a>Sintaxis

```
* cast-expression
```

## <a name="remarks"></a>Comentarios

El operador de direccionamiento indirecto unario (<strong>\*</strong>) desreferencia un puntero; es decir, convierte un valor de puntero a un valor l. El operando del operador de direccionamiento indirecto debe ser un puntero a un tipo. El resultado de la expresión de direccionamiento indirecto es el tipo del que se deriva el tipo de puntero. El uso de la <strong>\*</strong> operador en este contexto es diferente de su significado como operador binario, que es multiplicación.

Si el operando señala a una función, el resultado es un designador de función. Si señala a una ubicación de almacenamiento, el resultado es un valor L que designa la ubicación de almacenamiento.

El operador de direccionamiento indirecto se puede utilizar de manera acumulativa para desreferenciar punteros a punteros. Por ejemplo:

```cpp
// expre_Indirection_Operator.cpp
// compile with: /EHsc
// Demonstrate indirection operator
#include <iostream>
using namespace std;
int main() {
   int n = 5;
   int *pn = &n;
   int **ppn = &pn;

   cout  << "Value of n:\n"
         << "direct value: " << n << endl
         << "indirect value: " << *pn << endl
         << "doubly indirect value: " << **ppn << endl
         << "address of n: " << pn << endl
         << "address of n via indirection: " << *ppn << endl;
}
```

Si el valor de puntero no es válido, el resultado es indefinido. La lista siguiente incluye algunas de las condiciones más comunes que invalidan un valor de puntero.

- El puntero es un puntero null.

- El puntero especifica la dirección de un elemento local que no está visible en el momento de la referencia.

- El puntero especifica una dirección que está alineada de una forma no adecuada para el tipo de objeto al que se señala.

- El puntero especifica una dirección no utilizada por el programa que se ejecuta.

## <a name="see-also"></a>Vea también

[Expresiones con operadores unarios](../cpp/expressions-with-unary-operators.md)<br/>
[Operadores integrados de C++, precedencia y asociatividad](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[address-of (Operador): &](../cpp/address-of-operator-amp.md)<br/>
[Operadores de direccionamiento indirecto y address-of](../c-language/indirection-and-address-of-operators.md)