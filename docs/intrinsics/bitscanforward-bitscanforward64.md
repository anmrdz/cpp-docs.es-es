---
title: _BitScanForward, _BitScanForward64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
dev_langs:
- C++
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad699dc5e209dfae01bdaefdc8184c4cd2149aae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379689"
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Específicos de Microsoft**

Buscar los datos de máscara de bit menos significativo (LSB) a bit más significativo (LSB) para un bit establecido (1).

## <a name="syntax"></a>Sintaxis

```
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>Parámetros

*Index*<br/>
[out] Cargar con la posición del bit del primer bit establecido (1) se encuentra.

*Máscara*<br/>
[in] El valor de 32 bits o 64 bits para buscar.

## <a name="return-value"></a>Valor devuelto

0 si la máscara es cero; distinto de cero en caso contrario.

## <a name="remarks"></a>Comentarios

Si se encuentra un bit establecido, la posición de bit del primer bit establecido que se encontró se devuelve al primer parámetro. Si no se encuentra ningún bit establecido, se devuelve 0; de lo contrario, se devuelve 1.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64|
|`_BitScanForward64`|ARM, x64|

**Archivo de encabezado** \<intrin.h >

## <a name="example"></a>Ejemplo

```
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

## <a name="input"></a>Entrada

```
12
```

## <a name="sample-output"></a>Resultados del ejemplo

```
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)