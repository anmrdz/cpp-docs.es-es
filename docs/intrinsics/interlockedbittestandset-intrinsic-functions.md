---
title: funciones intrínsecas _interlockedbittestandset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _interlockedbittestandset_cpp
- _interlockedbittestandset_HLEAcquire
- _interlockedbittestandset64
- _interlockedbittestandset
- _interlockedbittestandset_rel
- _interlockedbittestandset64_HLEAcquire
- _interlockedbittestandset_HLERelease
- _interlockedbittestandset_acq
- _interlockedbittestandset_nf
- _interlockedbittestandset64_cpp
- _interlockedbittestandset64_HLERelease
dev_langs:
- C++
helpviewer_keywords:
- _interlockedbittestandset intrinsic
- _interlockedbittestandset64 intrinsic
- lock_bts instruction
ms.assetid: b1b7e334-53ea-48cf-ba60-5fa3ef51a1fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 406e3f974ce20068b183c9eab1f1f53bf113df78
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426840"
---
# <a name="interlockedbittestandset-intrinsic-functions"></a>Funciones intrínsecas _interlockedbittestandset

**Específicos de Microsoft**

Generar una instrucción que examina el bit `b` de la dirección `a` y devuelve su valor actual antes de establecerla a 1.

## <a name="syntax"></a>Sintaxis

```
unsigned char _interlockedbittestandset(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_acq(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_HLEAcquire(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_HLERelease(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_nf(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_rel(
   long *a,
   long b
);
unsigned char _interlockedbittestandset64(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLERelease(
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

El valor del bit en la posición `b` antes de establecerse.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|Header|
|---------------|------------------|------------|
|`_interlockedbittestandset`|x86, ARM, x64|\<INTRIN.h >|
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM|\<INTRIN.h >|
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, x64|\<immintrin.h >|
|`_interlockedbittestandset64`|x64|\<INTRIN.h >|
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|x64|\<immintrin.h >|

## <a name="remarks"></a>Comentarios

En procesadores x86 y x64, estos intrínsecos usan la `lock bts` instrucción para leer y establecer el bit especificado en 1. La operación es atómica.

En procesadores ARM, utilice los intrínsecos con sufijos `_acq` y `_rel` para adquirir y liberar semántica, como al principio y al final de una sección crítica. Los intrínsecos ARM con un sufijo `_nf` ("sin límite") no actúan como una barrera de memoria.

En las plataformas de Intel que admiten instrucciones de Elisión de bloqueo de Hardware (HLE), los intrínsecos con sufijos `_HLEAcquire` y `_HLERelease` incluyen una sugerencia para el procesador que puede acelerar el rendimiento mediante la eliminación de un paso de escritura de bloqueo en el hardware. Si se llama a estos intrínsecos en procesadores que no son compatibles con HLE, se omite la sugerencia.

Estas rutinas solo están disponibles como intrínsecos.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)<br/>
[Conflictos con el compilador de x86](../build/conflicts-with-the-x86-compiler.md)