---
title: Conversiones aritméticas habituales | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arithmetic conversions [C++]
- type conversion [C++], arithmetic
- operators [C], arithmetic conversions
- data type conversion [C++], arithmetic
- conversions [C++], arithmetic
- arithmetic operators [C++], type conversions
ms.assetid: bfa49803-0efd-45d0-b987-111412a140d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15ceaa3e5b50fbc72d14564630399b5e5ba74b49
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030436"
---
# <a name="usual-arithmetic-conversions"></a>Conversiones aritméticas habituales

La mayoría de los operadores de C realizan conversiones de tipos para llevar los operandos de una expresión a un tipo común o para ampliar valores cortos al tamaño entero usado en operaciones de equipo. Las conversiones realizadas por operadores de C dependen del operador específico y del tipo del operando o de los operandos. Sin embargo, muchos operadores realizan conversiones similares en los operandos de tipos enteros y de punto flotante. Estas conversiones se conocen como “conversiones aritméticas”. La conversión de un valor de operando a un tipo compatible no produce ningún cambio en el valor.

Las conversiones aritméticas que se resumen a continuación se denominan “conversiones aritméticas habituales”. Estos pasos solo se aplican a los operadores binarios que esperan un tipo aritmético. El propósito es producir un tipo común que también es el tipo de resultado. Para determinar qué conversiones tienen lugar realmente, el compilador aplica el algoritmo siguiente a las operaciones binarias de la expresión. Los pasos siguientes no son un orden de prioridad.

1. Si alguno de los operandos es de tipo `long double`, el otro operando se convierte al tipo `long double`.

1. Si la condición anterior no se cumple y cualquiera de los operandos es de tipo **double**, el otro operando se convierte al tipo **double**.

1. Si no se cumplen las dos condiciones anteriores y cualquiera de los operandos es de tipo **float**, el otro operando se convierte al tipo **float**.

1. Si no se cumplen las tres condiciones anteriores (ninguno de los operandos es de tipo de punto flotante), las conversiones enteras se realizan en los operandos de la manera siguiente:

   - Si alguno de los operandos es de tipo `unsigned long`, el otro operando se convierte al tipo `unsigned long`.

   - Si no se satisface la condición anterior y alguno de los operandos es de tipo **long** y el otro de tipo `unsigned int`, ambos operandos se convierten al tipo `unsigned long`.

   - Si las dos condiciones anteriores no se cumplen y alguno de los operandos es de tipo **long**, el otro operando se convierte al tipo **long**.

   - Si las tres condiciones anteriores no se cumplen y alguno de los operandos es de tipo `unsigned int`, el otro operando se convierte al tipo `unsigned int`.

   - Si no se cumple ninguna de las condiciones anteriores, ambos operandos se convierten al tipo `int`.

El código siguiente muestra estas reglas de conversión:

```
float   fVal;
double  dVal;
int   iVal;
unsigned long ulVal;

dVal = iVal * ulVal; /* iVal converted to unsigned long
                      * Uses step 4.
                      * Result of multiplication converted to double
                      */
dVal = ulVal + fVal; /* ulVal converted to float
                      * Uses step 3.
                      * Result of addition converted to double
                      */
```

## <a name="see-also"></a>Vea también

[Operadores de C](../c-language/c-operators.md)