---
title: _chdrive | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- chdrive
- _chdrive
dev_langs:
- C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b6d8d53ea3b7331de08ea2aa2a00e5fdfb106c8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684328"
---
# <a name="chdrive"></a>_chdrive

Cambia la unidad de trabajo actual.

> [!IMPORTANT]
> Esta API no se puede usar en aplicaciones que se ejecutan en Windows en tiempo de ejecución. Para obtener más información, vea [Funciones de CRT no admitidas en aplicaciones de la Plataforma universal de Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sintaxis

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Parámetros

*Unidad*<br/>
Entero de 1 a 26 que especifica la unidad de trabajo actual (1=A, 2=B, etc.).

## <a name="return-value"></a>Valor devuelto

Cero (0) si la unidad de trabajo actual se ha cambiado correctamente; de lo contrario, -1.

## <a name="remarks"></a>Comentarios

Si *unidad* está fuera del intervalo comprendido entre 1 y 26, se invoca el controlador de parámetros no válidos, como se describe en [validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, el **_chdrive** función devuelve -1, **errno** está establecido en **EACCES**, y **_doserrno** está establecido en  **ERROR_INVALID_DRIVE**.

La función **_chdrive** no es segura para subprocesos porque depende de la función **SetCurrentDirectory**, que a su vez no es segura para subprocesos. Para usar **_chdrive** de forma segura en una aplicación multiproceso, debe proporcionar su propia sincronización de subprocesos. Para obtener más información, consulte [SetCurrentDirectory](/windows/desktop/api/winbase/nf-winbase-setcurrentdirectory).

La función **_chdrive** solo cambia la unidad de trabajo actual; **_chdir** cambia el directorio de trabajo actual.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

Para obtener más información, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

Consulte el ejemplo de [_getdrive](getdrive.md).

## <a name="see-also"></a>Vea también

[Control de directorio](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
