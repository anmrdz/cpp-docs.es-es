---
title: Argumentos predeterminados | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- function declarators
- functions [C++], default arguments
- declaring functions [C++], declarators
- default arguments
- arguments [C++], default
- defaults [C++], arguments
ms.assetid: d32cf516-05cb-4d4d-b169-92f5649fdfa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48261d545737215ff44b1b56bb3b2d48839b6eb4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067064"
---
# <a name="default-arguments"></a>Argumentos predeterminados

En muchos casos, las funciones tienen argumentos que se usan con tan poca frecuencia que un valor predeterminado sería suficiente. Para resolver esto, la capacidad de argumento predeterminado permite especificar solo los argumentos de una función que son significativos en una llamada determinada. Para ilustrar este concepto, considere el ejemplo presentado en [sobrecarga de funciones](../cpp/function-overloading.md).

```cpp
// Prototype three print functions.
int print( char *s );                  // Print a string.
int print( double dvalue );            // Print a double.
int print( double dvalue, int prec );  // Print a double with a
//  given precision.
```

En muchas aplicaciones, se puede proporcionar un valor predeterminado razonable para `prec`, eliminando la necesidad de dos funciones:

```cpp
// Prototype two print functions.
int print( char *s );                    // Print a string.
int print( double dvalue, int prec=2 );  // Print a double with a
//  given precision.
```

La implementación de la `print` función cambia ligeramente para reflejar el hecho de que existe sólo una función de tipo **doble**:

```cpp
// default_arguments.cpp
// compile with: /EHsc /c

// Print a double in specified precision.
//  Positive numbers for precision indicate how many digits
//  precision after the decimal point to show. Negative
//  numbers for precision indicate where to round the number
//  to the left of the decimal point.

#include <iostream>
#include <math.h>
using namespace std;

int print( double dvalue, int prec ) {
   // Use table-lookup for rounding/truncation.
   static const double rgPow10[] = {
      10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,
         10E1,  10E2,  10E3,  10E4, 10E5,  10E6
   };
   const int iPowZero = 6;
   // If precision out of range, just print the number.
   if( prec >= -6 && prec <= 7 )
      // Scale, truncate, then rescale.
      dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *
      rgPow10[iPowZero - prec];
   cout << dvalue << endl;
   return cout.good();
}
```

Para invocar la nueva función `print`, use código tal como el siguiente:

```cpp
print( d );    // Precision of 2 supplied by default argument.
print( d, 0 ); // Override default argument to achieve other
//  results.
```

Tenga en cuenta los siguientes puntos al utilizar argumentos predeterminados:

- Los argumentos predeterminados solo se usan en las llamadas de función donde se omiten los argumentos de finalización; deben ser los últimos argumentos. Por consiguiente, el código siguiente no es válido:

    ```cpp
    int print( double dvalue = 0.0, int prec );
    ```

- Un argumento predeterminado no se puede volver a definir en declaraciones posteriores aunque la redefinición sea idéntica al original. Por lo tanto, el siguiente código produce un error:

    ```cpp
    // Prototype for print function.
    int print( double dvalue, int prec = 2 );

    ...

    // Definition for print function.
    int print( double dvalue, int prec = 2 )
    {
    ...
    }
    ```

   El problema con este código es que la declaración de función de la definición vuelve a definir el argumento predeterminado para `prec`.

- Declaraciones posteriores pueden agregar argumentos predeterminados adicionales.

- Se puede proporcionar argumentos predeterminados para punteros a funciones. Por ejemplo:

    ```cpp
    int (*pShowIntVal)( int i = 0 );
    ```