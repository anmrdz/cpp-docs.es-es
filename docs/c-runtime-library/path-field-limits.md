---
title: Límites del campo de ruta de acceso | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs:
- C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0672245a87cdbcf2a4a6dba6d36c675f3faafbc5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390399"
---
# <a name="path-field-limits"></a>Límites del campo de ruta de acceso

## <a name="syntax"></a>Sintaxis

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>Comentarios

Estas constantes definen la longitud máxima de la ruta de acceso y de los campos individuales dentro de dicha ruta.

|Constante|Significado|
|--------------|-------------|
|`_MAX_DIR`|Longitud máxima de componentes de directorio|
|`_MAX_DRIVE`|Longitud máxima de componentes de unidad|
|`_MAX_EXT`|Longitud máxima de componentes de extensión|
|`_MAX_FNAME`|Longitud máxima de componentes de nombre de archivo|
|`_MAX_PATH`|Longitud máxima de ruta de acceso completa|

> [!NOTE]
> C Runtime admite longitudes de ruta de acceso de hasta 32 768 caracteres, pero depende del sistema operativo, específicamente del sistema de archivos, que se admitan o no estas rutas de acceso más largas. La suma de los campos no puede exceder `_MAX_PATH` a efectos de compatibilidad total con versiones anteriores de los sistemas de archivos FAT32. El sistema de archivos NTFS de Windows es compatible con las rutas de acceso de hasta 32768 caracteres de longitud, pero únicamente cuando se usan las API Unicode. Al usar nombres de ruta de acceso largos, agregue el prefijo \\\\?\ a la ruta de acceso y use las versiones Unicode de las funciones de C Runtime.

## <a name="see-also"></a>Vea también

[Constantes globales](../c-runtime-library/global-constants.md)