---
title: Otros manipuladores de flujos de salida con un argumento | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams, one-argument manipulators
ms.assetid: e381dee8-6b16-4cef-805a-4a6a1d2b696b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30523a7db07dba1359af59c9fcc988feb0e4ec18
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953831"
---
# <a name="other-one-argument-output-stream-manipulators"></a>Otros manipuladores de flujos de salida con un argumento

En el ejemplo siguiente se usa una clase `money`, que es un **largo** tipo. El manipulador `setpic` adjunta una cadena formato de "imagen" a la clase que puede usarse mediante el operador de inserción de secuencia sobrecargado de la clase `money`. La cadena de imagen se almacena como una variable estática en la clase `money` en lugar de como un miembro de datos de una clase de secuencia, por lo que no tiene que derivar una nueva clase de flujo de salida.

## <a name="example"></a>Ejemplo

```cpp
// one_arg_output.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

typedef char* charp;

class money
{
private:
    long value;
    static char *szCurrentPic;
public:
    money( long val ) { value = val; }
    friend ostream& operator << ( ostream& os, money m ) {
        // A more complete function would merge the picture
        // with the value rather than simply appending it
        os << m.value << '[' << money::szCurrentPic << ']';
        return os;
    }
    static void setpic( char* szPic ) {
        money::szCurrentPic = new char[strlen( szPic ) + 1];
        strcpy_s( money::szCurrentPic, strlen( szPic ) + 1, szPic );
    }
};

char *money::szCurrentPic;  // Static pointer to picture

void fb( ios_base& os, char * somename )
{
   money::setpic(somename);
/*
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
*/
}

_Smanip<charp>
   __cdecl setpic(char * somename)
   {
   return (_Smanip<charp>(&fb, somename));
   }

int main( )
{
    money amt = (long)35235.22;
    cout << setiosflags( ios::fixed );
    cout << setpic( "###,###,###.##" ) << "amount = " << amt << endl;
}
```

## <a name="see-also"></a>Vea también

[Manipuladores personalizados con argumentos](../standard-library/custom-manipulators-with-arguments.md)<br/>
