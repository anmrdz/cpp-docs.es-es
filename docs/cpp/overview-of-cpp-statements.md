---
title: Información general sobre instrucciones de C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8836f3c82ea21d2ef22ccd3439dff3644380678
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030448"
---
# <a name="overview-of-c-statements"></a>Información general sobre las instrucciones de C++

Las instrucciones de C++ se ejecutan secuencialmente, excepto cuando una instrucción de expresión, una instrucción de selección, una instrucción de iteración o una instrucción de salto modifica específicamente esa secuencia.

Las instrucciones pueden ser de los tipos siguientes:

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

En la mayoría de los casos, la sintaxis de instrucción de C++ es idéntica de ANSI C. La diferencia principal entre los dos es que en C, se permiten declaraciones solo al principio de un bloque; C++ agrega el *instrucción de declaración*, que elimina eficazmente esta restricción. Esto permite introducir variables en un punto del programa donde se puede calcular un valor de inicialización precalculado.

Declarar variables dentro de bloques también permite controlar con precisión el ámbito y la duración de esas variables.

Los temas sobre instrucciones describen las siguientes palabras clave de C++:

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>Vea también

[Instrucciones](../cpp/statements-cpp.md)