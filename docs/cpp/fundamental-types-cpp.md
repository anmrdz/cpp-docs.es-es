---
title: Tipos fundamentales (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
dev_langs:
- C++
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7abb1efa9ca7260648574299cde454a33f84b3f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114896"
---
# <a name="fundamental-types--c"></a>Tipos fundamentales (C++)

Los tipos fundamentales de C++ se dividen en tres categorías: entero, punto flotante y void. Los tipos enteros son capaces de controlar números enteros. Los tipos de punto flotante son capaces de especificar valores que pueden tener partes fraccionarias.

El tipo [void](../cpp/void-cpp.md) describe un conjunto de valores vacío. No hay ninguna variable de tipo **void** puede especificarse: se usa principalmente para declarar funciones que no devuelven ningún valor o declarar punteros genéricos a sin tipo o de forma arbitraria con el tipo de datos. Cualquier expresión se puede convertir explícitamente o convertir al tipo **void**. Sin embargo, estas expresiones se limitan a los siguientes usos:

- Una instrucción de expresión. (Vea [Expresiones](../cpp/expressions-cpp.md)para obtener más información).

- El operando izquierdo del operador de coma. (Vea [Operador de coma](../cpp/comma-operator.md) para obtener más información).

- El segundo o tercer operando del operador condicional (`? :`). (Vea [Expresiones con el operador condicional](../cpp/conditional-operator-q.md) para obtener más información).

En la tabla siguiente se explican las restricciones en los tamaños de tipo. Estas restricciones son independientes de la implementación de Microsoft.

### <a name="fundamental-types-of-the-c-language"></a>Tipos fundamentales del lenguaje C++

|Categoría|Tipo|Contenido|
|--------------|----------|--------------|
|Entero|**char**|Tipo **char** es un tipo entero que normalmente contiene miembros del juego de caracteres básico de ejecución, de forma predeterminada, es ASCII, en Microsoft C++.<br /><br /> El compilador de C++ trata las variables de tipo **char**, **firmado char**, y **unsigned char** como si tuvieran tipos diferentes. Las variables de tipo **char** se promueven a **int** como si fueran de tipo **firmado char** de forma predeterminada, a menos que se usa la opción de compilación/j. En este caso se tratan como tipo **unsigned char** y se promueven a **int** sin extensión de signo.|
||**bool**|Tipo **bool** es un tipo entero que puede tener uno de los dos valores **true** o **false**. Su tamaño no está especificado.|
||**short**|Tipo **short int** (o simplemente **corto**) es un tipo entero que es mayor que o igual que el tamaño del tipo **char**y menor o igual que el tamaño del tipo **int**.<br /><br /> Los objetos de tipo **corto** se pueden declarar como **firmado resumen** o **entero corto sin signo**. **Resumen firmado** es un sinónimo de **corto**.|
||**int**|Tipo **int** es un tipo entero que es mayor que o igual que el tamaño del tipo **short int**y menor o igual que el tamaño del tipo **largo**.<br /><br /> Los objetos de tipo **int** se pueden declarar como **firmado int** o **int sin signo**. **Firmado int** es un sinónimo de **int**.|
||**__int8**, **__int16**, **__int32**, **__int64**|En el entero con tamaño `__int n`, `n` es el tamaño, en bits, de la variable de entero. **__int8**, **__int16**, **__int32** y **__int64** son palabras clave específicas de Microsoft. No todos los tipos están disponibles en todas las arquitecturas. (**__int128** no se admite.)|
||**long**|Tipo **largo** (o **long int**) es un tipo entero que es mayor que o igual que el tamaño del tipo **int**.<br /><br /> Los objetos de tipo **largo** se pueden declarar como **long con signo** o **unsigned long**. **Long con signo** es un sinónimo de **largo**.|
||**long long**|Mayor que unsigned **largo**.<br /><br /> Los objetos de tipo **long long** se pueden declarar como **long long con signo** o **long long sin signo**. **long long con signo** es un sinónimo de **long long**.|
||**wchar_t**, **__wchar_t**|Una variable de tipo **wchar_t** designa un tipo de caracteres anchos o multibyte. De forma predeterminada, **wchar_t** es un tipo nativo, pero puede usar [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) realizar **wchar_t** un typedef para **entero corto sin signo**. El **__wchar_t** tipo es un sinónimo específico de Microsoft para nativo **wchar_t** tipo.<br /><br /> Use el prefijo L delante de un carácter o un literal de cadena para designar el tipo de carácter ancho.|
|Punto flotante|**float**|Tipo **float** es flotante más pequeño tipo de punto.|
||**double**|Tipo **doble** es un tipo de punto flotante que es mayor que o igual al tipo **float**, pero inferior o igual que el tamaño del tipo **long double**.<br /><br /> Específico de Microsoft: la representación de **long double** y **doble** es idéntico. Sin embargo, **long double** y **doble** son tipos distintos.|
||**long double**|Tipo **long double** es un tipo que es mayor que o igual al tipo flotante **doble**.|

**Específicos de Microsoft**

En la tabla siguiente se muestra la cantidad de almacenamiento necesaria para los tipos fundamentales de Microsoft C++.

### <a name="sizes-of-fundamental-types"></a>Tamaños de los tipos fundamentales

|Tipo|Tamaño|
|----------|----------|
|**BOOL**, **char**, **unsigned char**, **firmado char**, **__int8**|1 byte|
|**__int16**, **corto**, **entero corto sin signo**, **wchar_t**, **__wchar_t**|2 bytes|
|**float**, **__int32**, **int**, **int sin signo**, **largo**, **unsigned long**|4 bytes|
|**Double**, **__int64**, **long double**, **long long**|8 bytes|

**FIN de Específicos de Microsoft**

Vea [Intervalos de tipo de datos](../cpp/data-type-ranges.md) para obtener un resumen del intervalo de valores de cada tipo.

Para obtener más información sobre la conversión de tipos, vea [Conversiones estándar](../cpp/standard-conversions.md).

## <a name="see-also"></a>Vea también

[Intervalos de tipo de datos](../cpp/data-type-ranges.md)