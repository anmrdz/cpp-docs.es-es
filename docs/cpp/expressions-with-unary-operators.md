---
title: Expresiones con operadores unarios | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 718b27d14414480a3515a212bc0b272e8cfbb7c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017877"
---
# <a name="expressions-with-unary-operators"></a>Expresiones con operadores unarios

Los operadores unarios actúan solo sobre un operando en una expresión. Los operadores unarios son los siguientes:

- [Operador de direccionamiento indirecto (*)](../cpp/indirection-operator-star.md)

- [Operador Address-of (&)](../cpp/address-of-operator-amp.md)

- [Unario más (+), operador](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Operador unario de negación (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Operador lógico de negación (!)](../cpp/logical-negation-operator-exclpt.md)

- [Operador complementario (~)](../cpp/one-s-complement-operator-tilde.md)

- [Operador de incremento de prefijo (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Operador de decremento de prefijo (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Operador de conversión)](../cpp/cast-operator-parens.md)

- [operador sizeof](../cpp/sizeof-operator.md)

- [__uuidof (operador)](../cpp/uuidof-operator.md)

- [__alignof (operador)](../cpp/alignof-operator.md)

- [New (operador)](../cpp/new-operator-cpp.md)

- [Delete (operador)](../cpp/delete-operator-cpp.md)

Estos operadores tienen asociatividad de derecha a izquierda. Las expresiones unarias normalmente usan sintaxis que precede a una expresión de postfijo o primaria.

Estas son las posibles formas de expresiones unarias.

- *postfix-expression*

- `++` *unary-expression*

- `--` *unary-expression*

- *operador unario* *unary-expression*

- **sizeof** *unary-expression*

- `sizeof(` *nombre de tipo* `)`

- `decltype(` *Expresión* `)`

- *expresión de asignación*

- *expresión de desasignación*

Cualquier *postfix-expression* se considera un *unary-expression*, y dado que cualquier expresión primaria se considera un *postfix-expression*, es cualquier expresión primaria considera un *unary-expression* también. Para obtener más información, consulte [expresiones de postfijo](../cpp/postfix-expressions.md) y [expresiones primarias](../cpp/primary-expressions.md).

Un *unary-operator* consta de uno o varios de los siguientes símbolos: `* & + - ! ~`

El *unary-expression* es una expresión unaria con una conversión opcional para cambiar el tipo. Para obtener más información, consulte [operador de conversión: ()](../cpp/cast-operator-parens.md).

Un *expresión* puede ser cualquier expresión. Para obtener más información, consulte [expresiones](../cpp/expressions-cpp.md).

El *expresión de asignación* hace referencia a la **nuevo** operador. El *desasignación expresión* hace referencia a la **eliminar** operador. Para obtener más información, vea los vínculos anteriores en este tema.

## <a name="see-also"></a>Vea también

[Tipos de expresiones](../cpp/types-of-expressions.md)