---
title: funciones intrínsecas _interlockedbittestandreset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _interlockedbittestandreset_rel
- _interlockedbittestandreset64
- _interlockedbittestandreset64_HLERelease
- _interlockedbittestandreset_HLERelease
- _interlockedbittestandreset_HLEAcquire
- _interlockedbittestandreset_acq
- _interlockedbittestandreset_cpp
- _interlockedbittestandreset_nf
- _interlockedbittestandreset64_cpp
- _interlockedbittestandreset64_HLEAcquire
- _interlockedbittestandreset
dev_langs:
- C++
helpviewer_keywords:
- lock_btr instruction
- _interlockedbittestandreset64 intrinsic
- _interlockedbittestandreset intrinsic
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6916b746aac8bbd4b1008289ec2eacd3afaa5571
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447662"
---
# <a name="interlockedbittestandreset-intrinsic-functions"></a>Funciones intrínsecas _interlockedbittestandreset

**Específicos de Microsoft**

Genera una instrucción que establece el bit `b` de la dirección `a` en cero y devuelve su valor original.

## <a name="syntax"></a>Sintaxis

```
unsigned char _interlockedbittestandreset(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_acq(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_HLEAcquire(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_HLERelease(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_nf(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_rel(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset64(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLERelease(
   __int64 *a,
   __int64 b
);
```

#### <a name="parameters"></a>Parámetros

*a*<br/>
[in] Un puntero a la memoria que se va a examinar.

*b*<br/>
[in] La posición de bit para probar.

## <a name="return-value"></a>Valor devuelto

El valor original del bit en la posición especificada por `b`.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|Header|
|---------------|------------------|------------|
|`_interlockedbittestandreset`|x86, ARM, x64|\<INTRIN.h >|
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\<INTRIN.h >|
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, x64|\<immintrin.h >|
|`_interlockedbittestandreset64`|x64|\<INTRIN.h >|
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|x64|\<immintrin.h >|

## <a name="remarks"></a>Comentarios

En procesadores x86 y x64, estos intrínsecos usan la `lock btr` instrucción, que lee y establece el bit especificado en cero en una operación atómica.

En procesadores ARM, utilice los intrínsecos con sufijos `_acq` y `_rel` para adquirir y liberar semántica, como al principio y al final de una sección crítica. Los intrínsecos ARM con un sufijo `_nf` ("sin límite") no actúan como una barrera de memoria.

En las plataformas de Intel que admiten instrucciones de Elisión de bloqueo de Hardware (HLE), los intrínsecos con sufijos `_HLEAcquire` y `_HLERelease` incluyen una sugerencia para el procesador que puede acelerar el rendimiento mediante la eliminación de un paso de escritura de bloqueo en el hardware. Si se llama a estos intrínsecos en procesadores que no son compatibles con HLE, se omite la sugerencia.

Estas rutinas solo están disponibles como intrínsecos.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)<br/>
[Conflictos con el compilador de x86](../build/conflicts-with-the-x86-compiler.md)