---
title: feclearexcept1 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feclearexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: face2637f308a56d95baa7563a6409dd38870d73
ms.sourcegitcommit: 2f571220e16f6c20e1fdb005f6cbc9e7ef5608f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2018
ms.locfileid: "37070082"
---
# <a name="feclearexcept"></a>feclearexcept

Intenta borrar las marcas de excepción de punto flotante especificadas por el argumento.

## <a name="syntax"></a>Sintaxis

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>Parámetros

*excepts*<br/>
Marcas de estado de excepción que se borran.

## <a name="return-value"></a>Valor devuelto

Devuelve cero si *excepts* es cero, o si todas las excepciones especificadas se borraron correctamente. De lo contrario, devuelve un valor distinto de cero.

## <a name="remarks"></a>Comentarios

El **feclearexcept** función intenta borrar flotante punto marcas de estado de excepción especificados por *excepts*. La función admite estas macros de excepción, que se definen en fenv.h:

|Macro de excepción|Descripción|
|---------------------|-----------------|
|FE_DIVBYZERO|Se ha producido un error de singularidad o de polo en una operación de punto flotante anterior; se ha creado un valor infinito.|
|FE_INEXACT|Se ha forzado la función a redondear el resultado almacenado de una operación de punto flotante anterior.|
|FE_INVALID|Se ha producido un error de dominio en una operación de punto flotante anterior.|
|FE_OVERFLOW|Se ha producido un error de intervalo; el resultado de una operación de punto flotante anterior era demasiado grande para representarse.|
|FE_UNDERFLOW|El resultado de una operación de punto flotante anterior era demasiado pequeño para representarlo con completa precisión; se ha creado un valor no normalizado.|
|FE_ALL_EXCEPT|Operación OR bit a bit de todas las excepciones de punto flotante admitidas.|

El *excepts* argumento puede ser cero o la operación OR bit a bit de uno o más de las macros de excepción admitidos. El resultado de cualquier otro valor de argumento es indefinido.

## <a name="requirements"></a>Requisitos

|Función|Encabezado C|Encabezado C++|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Vea también

[Referencia alfabética de funciones](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
