---
title: _msize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _msize
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9e27751072891bcabc0b068cb5ca57b571d35d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402158"
---
# <a name="msize"></a>_msize

Devuelve el tamaño de un bloque de memoria asignado en el montón.

## <a name="syntax"></a>Sintaxis

```C
size_t _msize(
   void *memblock
);
```

### <a name="parameters"></a>Parámetros

*memblock*<br/>
Puntero al bloque de memoria.

## <a name="return-value"></a>Valor devuelto

**_msize** devuelve el tamaño (en bytes) como un entero sin signo.

## <a name="remarks"></a>Comentarios

El **_msize** función devuelve el tamaño, en bytes, del bloque de memoria asignada por una llamada a **calloc**, **malloc**, o **realloc**.

Cuando la aplicación se vincula con una versión de depuración de las bibliotecas de tiempo de ejecución de C, **_msize** se resuelve como [_msize_dbg](msize-dbg.md). Para obtener más información sobre cómo se administra el montón durante el proceso de depuración, consulte [Detalles del montón de depuración de CRT](/visualstudio/debugger/crt-debug-heap-details).

Esta función valida su parámetro. Si *memblock* es un puntero nulo, **_msize** invoca un controlador de parámetros no válidos, tal y como se describe en [validación de parámetros](../../c-runtime-library/parameter-validation.md). Si se controla el error, la función establece **errno** a **EINVAL** y devuelve -1.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotecas

Todas las versiones de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Ejemplo

Vea el ejemplo de [realloc](realloc.md).

## <a name="see-also"></a>Vea también

[Asignación de memoria](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[_expand](expand.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
