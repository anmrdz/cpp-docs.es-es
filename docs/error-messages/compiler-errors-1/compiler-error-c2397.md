---
title: Error del compilador C2397 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3e76384ca2509663398fd7abd7badfd4057e8c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115104"
---
# <a name="compiler-error-c2397"></a>Error del compilador C2397

conversión de 'type_1' a 'type_2' requiere una conversión de restricción

Se encontró una conversión de restricción implícita cuando se usa la inicialización uniforme.

Conversiones de restricción implícitas en las asignaciones y la inicialización permite que el lenguaje C y C++ sigue palo, aunque inesperado de restricción es una causa de muchos errores de código. Para mejorar la seguridad de código, el estándar de C++ requiere un mensaje de diagnóstico cuando se produce una conversión de restricción en una lista de inicialización. En Visual C++, el diagnóstico es Error del compilador C2397 cuando se usa el principio de la sintaxis admitida de inicialización uniforme en Visual Studio 2015. El compilador genera [advertencia del compilador (nivel 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) cuando se usa la lista o la sintaxis de inicialización de agregado compatibles con Visual Studio 2013.

Una conversión de restricción puede ser correcta cuando se sabe que el intervalo posible de los valores convertidos puede caber en el destino. En este caso, sabrá que más de lo que hace el compilador. Si realiza una conversión de restricción intencionadamente, hacer que sus intenciones explícito mediante el uso de una conversión estática. En caso contrario, este mensaje de error casi siempre indica que hay un error en el código. Puede corregirlo asegurándose de que los objetos que se inicializa con tipos que son lo suficientemente grandes como para controlar las entradas.

El ejemplo siguiente genera C2397 y muestra una forma de corregirlo:

```
// C2397.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C2397.cpp
#include <vector>

struct S1 {
    int m1;
    double m2, m3;
};

void function_C2397(double d1) {
    char c1 { 127 };          // OK
    char c2 { 513 };          // error C2397

    std::vector<S1> vS1;
    vS1.push_back({ d1, 2, 3 }); // error C2397

    // Possible fix if you know d1 always fits in an int
    vS1.push_back({ static_cast<int>(d1), 2, 3 });
}
```