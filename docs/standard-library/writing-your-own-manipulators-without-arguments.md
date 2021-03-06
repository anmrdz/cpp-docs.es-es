---
title: Escribir manipuladores propios sin argumentos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8bfad1919863a58554604fe6d32b4563e57a14a
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235716"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Escribir manipuladores propios sin argumentos

Escribir manipuladores que no usan argumentos no requiere la derivación de clases ni el uso de macros complejas. Supongamos que su impresora requiere el par \<ESC >[ para entrar en modo de negrita. Puede insertar este par directamente en la secuencia:

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

O puede definir el manipulador `bold`, que inserta los caracteres:

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

La función `bold` definida globalmente toma un argumento de referencia `ostream` y devuelve la referencia `ostream`. No es una función miembro ni una función friend porque no necesita tener acceso a los elementos de ninguna clase privada. La función `bold` se conecta a la secuencia porque el operador `<<` de la secuencia se sobrecarga para aceptar este tipo de función, mediante una declaración de aspecto similar al siguiente:

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

Puede usar esta característica para ampliar otros operadores sobrecargados. En este caso, que `bold` inserte caracteres en la secuencia es algo eventual. La función se llama cuando se inserta en la secuencia, no necesariamente cuando se imprimen los caracteres adyacentes. Por tanto, la impresión podría retrasarse debido al almacenamiento en búfer de la secuencia.

## <a name="see-also"></a>Vea también

[Flujos de salida](../standard-library/output-streams.md)<br/>
