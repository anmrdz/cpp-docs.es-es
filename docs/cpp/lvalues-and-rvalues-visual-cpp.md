---
title: 'Categorías de valor: Lvalues y Rvalues (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f19a06ac0583dd4cb911818787408aeca30b2ec
ms.sourcegitcommit: 2f84d56b6ab19ba745b32ecd96b193c73cd62adf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48866220"
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalues y Rvalues (Visual C++)

Cada expresión de C++ tiene un tipo y pertenece a un *categoría valor*. Las categorías de valor son la base para las reglas que los compiladores deben seguir al crear, copiar y mover objetos temporales durante la evaluación de expresión.

El estándar C ++ 17 define las categorías de valor de expresión como sigue:

- Un *glvalue* es una expresión cuya evaluación determina la identidad de un objeto, el campo de bits o la función.
- Un *prvalue* es una expresión cuya evaluación Inicializa un objeto o un campo de bits, o calcula el valor del operando de un operador, como especificado por el contexto donde aparece.
- Un *xvalue* es un glvalue que denota un objeto o un campo de bits cuyos recursos se pueden reutilizar (normalmente porque es casi al final de su ciclo de vida). [Ejemplo: determinados tipos de expresiones que implican las referencias rvalue (8.3.2) producen xvalues, por ejemplo, una llamada a una función cuyo tipo de valor devuelto es una referencia rvalue o una conversión a un tipo de referencia rvalue. ]
- Un *lvalue* es un glvalue que no sea un xvalue.
- Un *rvalue* es un prvalue o un xvalue.

El siguiente diagrama muestra las relaciones entre las categorías:

![Categorías de valor de expresión de C++](media/value_categories.png "categorías de valor de expresión de C++")

Un valor l tiene una dirección que puede tener acceso su programa. Los nombres de variable, incluidos algunos ejemplos de expresiones de valor l **const** llamadas que devuelven una referencia lvalue, campos de bits, uniones y los miembros de clase de función de las variables, los elementos de matriz.

Una expresión de prvalue no tiene ninguna dirección que sea accesible para el programa. Ejemplos de expresiones prvalue incluyen literales, llamadas a funciones que devuelven un tipo sin referencia y los objetos temporales que se crean durante la evaluación de expresión, pero accesible únicamente por el compilador.

Una expresión xvalue tiene una dirección que ya no es accesible por el programa, pero se puede usar para inicializar una referencia rvalue, que proporciona acceso a la expresión. Algunos ejemplos son llamadas a funciones que devuelven una referencia rvalue y el subíndice de matriz, miembro y puntero a expresiones de miembro donde la matriz u objeto es una referencia rvalue.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestran varios usos correctos e incorrectos de valores L y valores R:

```cpp
// lvalues_and_rvalues2.cpp
int main()
{
    int i, j, *p;

    // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.
    i = 7;

    // Incorrect usage: The left operand must be an lvalue (C2106).`j * 4` is a prvalue.
    7 = i; // C2106
    j * 4 = 7; // C2106

    // Correct usage: the dereferenced pointer is an lvalue.
    *p = i;

    const int ci = 7;
    // Incorrect usage: the variable is a non-modifiable lvalue (C3892).
    ci = 9; // C3892

    // Correct usage: the conditional operator returns an lvalue.
    ((i < 3) ? i : j) = 7;
}
```

> [!NOTE]
> En los ejemplos de este tema se muestra el uso correcto e incorrecto cuando los operadores no están sobrecargados. Si sobrecarga operadores, puede convertir una expresión tal como `j * 4` en un valor L.

Los términos *lvalue* y *rvalue* a menudo se usan cuando se hace referencia a las referencias de objeto. Para obtener más información acerca de las referencias, vea [declarador de referencia Lvalue: &](../cpp/lvalue-reference-declarator-amp.md) y [declarador de referencia Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Vea también

[Conceptos básicos](../cpp/basic-concepts-cpp.md)<br/>
[Declarador de referencia a un valor L: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Declarador de referencia a un valor R: &&](../cpp/rvalue-reference-declarator-amp-amp.md)
