---
title: Operadores de &lt;istream&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::operator&gt;&gt;
dev_langs:
- C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82a5a02ed85e3a02c1131a413eb8588dd49dee90
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100903"
---
# <a name="ltistreamgt-operators"></a>Operadores de &lt;istream&gt;

## <a name="op_gt_gt"></a> operator&gt;&gt;

Extrae caracteres y cadenas del flujo.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Parámetros

*CH*<br/>
Un carácter.

*ISTR*<br/>
Flujo.

*str*<br/>
Una cadena.

*Val*<br/>
Un tipo.

### <a name="return-value"></a>Valor devuelto

Flujo.

### <a name="remarks"></a>Comentarios

La clase `basic_istream` también define varios operadores de extracción. Para obtener más información, vea [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

La función de plantilla:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

extrae hasta *N* - 1 elementos y los almacena en la matriz empezando por _ *Str*. Si `Istr`. [width](../standard-library/ios-base-class.md#width) es mayor que cero, *N* es `Istr`. **ancho**; en caso contrario, es el tamaño de la matriz más grande de `Elem` que se pueden declarar. La función siempre almacena el valor `Elem()` después de cualquier elemento extraído que almacene. La extracción se detiene anticipadamente al final del archivo, en un carácter con el valor **Elem**(0) (que no se extrae) o en cualquier elemento (que no se extrae) que [ws](../standard-library/istream-functions.md#ws) descartaría. Si la función no extrae ningún elemento, llama a `Istr`. [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**). En cualquier caso, llama a `Istr`. **ancho**(0) y devuelve *Istr*.

**Nota de seguridad** la cadena terminada en null que se va a extraer el flujo de entrada no puede superar el tamaño del búfer de destino *str*. Para obtener más información, vea [Avoiding Buffer Overruns](/windows/desktop/SecBP/avoiding-buffer-overruns)(Evitar saturaciones del búfer).

La función de plantilla:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

extrae un elemento, si es posible y lo almacena en *Ch*. En caso contrario, llama a **is**. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). En cualquier caso, devuelve *Istr*.

La función de plantilla:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

Devuelve `Istr >> ( char * ) str`.

La función de plantilla:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

Devuelve `Istr >> ( char& ) Ch`.

La función de plantilla:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

Devuelve `Istr >> ( char * ) str`.

La función de plantilla:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

Devuelve `Istr >> ( char& ) Ch`.

La función de plantilla:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

Devuelve `Istr >> val` (y convierte una referencia rvalue para `Istr` a un valor l en el proceso).

### <a name="example"></a>Ejemplo

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>Vea también

[\<istream>](../standard-library/istream.md)<br/>
