---
title: 'Cómo: convertir char * String en una matriz System:: Byte | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], strings
- arrays [C++], character
- character arrays, converting to System::Byte arrays
- examples [C++], arrays
ms.assetid: de9bc4eb-773c-4796-a496-9b90ca986503
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5485d52b54375f39cdc7fc4655c71e4877879062
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375953"
---
# <a name="how-to-convert-char--string-to-systembyte-array"></a>Cómo: convertir char \* String en una matriz System:: Byte

La manera más eficaz de convertir una cadena `char *` en una matriz <xref:System.Byte> es utilizando la clase <xref:System.Runtime.InteropServices.Marshal>.

## <a name="example"></a>Ejemplo

```
// convert_native_string_to_Byte_array.cpp
// compile with: /clr
#include <string.h>

using namespace System;
using namespace System::Runtime::InteropServices;

int main() {
   char buf[] = "Native String";
   int len = strlen(buf);

   array< Byte >^ byteArray = gcnew array< Byte >(len + 2);

   // convert native pointer to System::IntPtr with C-Style cast
   Marshal::Copy((IntPtr)buf,byteArray, 0, len);

   for ( int i = byteArray->GetLowerBound(0); i <= byteArray->GetUpperBound(0); i++ ) {
      char dc =  *(Byte^)   byteArray->GetValue(i);
      Console::Write((Char)dc);
   }

   Console::WriteLine();
}
```

```Output
Native String
```

## <a name="see-also"></a>Vea también

[Usar la interoperabilidad de C++ (PInvoke implícito)](../dotnet/using-cpp-interop-implicit-pinvoke.md)