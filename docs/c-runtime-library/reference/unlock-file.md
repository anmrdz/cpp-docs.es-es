---
title: _unlock_file | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _unlock_file
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
- _unlock_file
- unlock_file
dev_langs:
- C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63b0950aaea5520849f9a32b2b08ab138cd8099b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107552"
---
# <a name="unlockfile"></a>_unlock_file

Desbloquea un archivo para que otros procesos puedan acceder a él.

## <a name="syntax"></a>Sintaxis

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Parámetros

*file*<br/>
Identificador de archivo.

## <a name="remarks"></a>Comentarios

El **_unlock_file** función desbloquea el archivo especificado por *archivo*. El desbloqueo de un archivo permite que otros procesos accedan a él. Esta función no debe llamarse a menos que **_lock_file** se llamó previamente en el *archivo* puntero. Una llamada a **_unlock_file** en un archivo que no esté bloqueado puede provocar un interbloqueo. A modo de ejemplo, vea [_lock_file](lock-file.md).

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Vea también

[Control de archivos](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
