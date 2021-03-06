---
title: __shiftleft128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __shiftleft128
dev_langs:
- C++
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfbe0ba26d247891a26d87d9f7526cefc292d3fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436384"
---
# <a name="shiftleft128"></a>__shiftleft128

**Específicos de Microsoft**

Desplaza una cantidad de 128 bits, representada como dos cantidades de 64 bits `LowPart` y `HighPart`, a la izquierda según un número de bits especificado por `Shift` y devuelve los 64 bits superiores del resultado.

## <a name="syntax"></a>Sintaxis

```
unsigned __int64 __shiftleft128( 
   unsigned __int64 LowPart, 
   unsigned __int64 HighPart, 
   unsigned char Shift 
);
```

#### <a name="parameters"></a>Parámetros

*Parte inferior*<br/>
[in] Los 64 bits inferiores de la cantidad de 128 bits para desplazar.

*HighPart*<br/>
[in] Los 64 bits superiores de la cantidad de 128 bits para desplazar.

*Mayús*<br/>
[in] El número de bits del desplazamiento.

## <a name="return-value"></a>Valor devuelto

Los 64 bits superiores del resultado.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__shiftleft128`|x64|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

El valor `Shift` es siempre módulo 64 para que, por ejemplo, si se llama a `__shiftleft128(1, 0, 64)`, la función desplace los bits `0` de la parte baja a la izquierda y devuelva una parte alta de `0` en vez de `1`, como cabría esperar.

## <a name="example"></a>Ejemplo

```
// shiftleft128.c
// processor: IPF, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__shiftleft128, __shiftright128)

int main()
{
    unsigned __int64 i = 0x1I64;
    unsigned __int64 j = 0x10I64;
    unsigned __int64 ResultLowPart;
    unsigned __int64 ResultHighPart;

    ResultLowPart = i << 1;
    ResultHighPart = __shiftleft128(i, j, 1);

    // concatenate the low and high parts padded with 0's
    // to display correct hexadecimal 128 bit values
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);

    ResultHighPart = j >> 1;
    ResultLowPart = __shiftright128(i, j, 1);

    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);
}
```

```Output
0x100000000000000001 << 1 = 0x200000000000000002
0x100000000000000001 >> 1 = 0x080000000000000000
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[__shiftright128](../intrinsics/shiftright128.md)<br/>
[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)