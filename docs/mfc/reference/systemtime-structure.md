---
title: SYSTEMTIME (estructura) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6882a4e169b7efa67bef02ab5abee1276384e52f
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334573"
---
# <a name="systemtime-structure"></a>SYSTEMTIME (Estructura)

El `SYSTEMTIME` estructura representa una fecha y hora mediante miembros individuales para el mes, día, año, día de la semana, hora, minuto, segundo y milisegundo.

## <a name="syntax"></a>Sintaxis

```
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME;
```

#### <a name="parameters"></a>Parámetros

*wYear*<br/>
El año actual.

*wMonth*<br/>
El mes actual; Enero es 1.

*wDayOfWeek*<br/>
El día actual de la semana; El domingo es 0, el lunes es 1 y así sucesivamente.

*wDay*<br/>
El día actual del mes.

*wHour*<br/>
La hora actual.

*wMinute*<br/>
El minuto actual.

*wSecond*<br/>
El segundo actual.

*wMilliseconds*<br/>
El milisegundo actual.

## <a name="example"></a>Ejemplo

[!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]

## <a name="requirements"></a>Requisitos

**Encabezado:** winbase.h

## <a name="see-also"></a>Vea también

[Estructuras, estilos, devoluciones de llamada y mapas de mensajes](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime:: CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

