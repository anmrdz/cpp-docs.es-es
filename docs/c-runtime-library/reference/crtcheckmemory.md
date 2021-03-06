---
title: _CrtCheckMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtCheckMemory
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
apitype: DLLExport
f1_keywords:
- CrtCheckMemory
- _CrtCheckMemory
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6d4b84fd717525e7206956964204794fe6b88c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396669"
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

Confirma la integridad de los bloques de memoria asignados en el montón de depuración (solo versión de depuración).

## <a name="syntax"></a>Sintaxis

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Valor devuelto

Si se realiza correctamente, **_CrtCheckMemory** devuelve TRUE; en caso contrario, la función devuelve FALSE.

## <a name="remarks"></a>Comentarios

El **_CrtCheckMemory** función valida la memoria asignada por el administrador del montón de depuración comprobando el montón base subyacente e inspeccionando cada bloque de memoria. Si se produce una incoherencia de error o de memoria en el montón base subyacente, la información de encabezado de depuración o los búferes sobrescritos, **_CrtCheckMemory** genera un informe de depuración con información que describe la condición de error. Cuando [_DEBUG](../../c-runtime-library/debug.md) no está definido, las llamadas a **_CrtCheckMemory** se quitan durante el preprocesamiento.

El comportamiento de **_CrtCheckMemory** puede controlarse estableciendo los campos de bits de la [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) marca mediante el [_CrtSetDbgFlag](crtsetdbgflag.md) función. Activar la **_CRTDBG_CHECK_ALWAYS_DF** campo de bits en **_CrtCheckMemory** que se llama cada vez que se solicita una operación de asignación de memoria. Aunque este método ralentiza la ejecución, es útil para detectar errores rápidamente. Activar la **_CRTDBG_ALLOC_MEM_DF** causas OFF de campo de bits **_CrtCheckMemory** no comprobar el montón y devolver inmediatamente **TRUE**.

Dado que esta función devuelve **TRUE** o **FALSE**, se puede pasar a una de las macros [_ASSERT](assert-asserte-assert-expr-macros.md) para crear un mecanismo sencillo de control de errores de depuración. En el ejemplo siguiente se genera un error de aserción si se detectan daños en el montón:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Para obtener más información acerca de cómo **_CrtCheckMemory** puede utilizarse con otras funciones de depuración, consulte [funciones que indican el estado del montón](/visualstudio/debugger/crt-debug-heap-details). Para obtener información general sobre la administración de memoria y el montón de depuración, consulte [Detalles del montón de depuración de CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotecas

Solo versiones de depuración de las [bibliotecas en tiempo de ejecución de C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Ejemplo

Para obtener un ejemplo de cómo usar **_CrtCheckMemory**, consulte [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Vea también

[Rutinas de depuración](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
