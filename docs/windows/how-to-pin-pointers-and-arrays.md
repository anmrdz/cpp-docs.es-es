---
title: 'Cómo: anclar punteros y matrices | Microsoft Docs'
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7adf9d4d45b4acafd65adc27e28d8eb0639d32c8
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327900"
---
# <a name="how-to-pin-pointers-and-arrays"></a>Cómo: Anclar punteros y matrices

Anclar un subobjeto definido en un objeto administrado tiene el efecto de anclar todo el objeto.  Por ejemplo, si está anclada a cualquier elemento de una matriz, también se ancla la matriz entera. No hay ninguna extensión al lenguaje para declarar una matriz anclada. Para anclar una matriz, declarar un puntero anclado a su tipo de elemento y ancla una de sus elementos.

## <a name="example"></a>Ejemplo

### <a name="code"></a>Código

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>Vea también

[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)