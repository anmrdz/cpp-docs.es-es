---
title: Funciones globales de control de eventos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ef89aec3a0eaf53c6c97b3480008b7e9fd586e3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054896"
---
# <a name="event-handling-global-functions"></a>Funciones globales de control de eventos

Esta función proporciona un controlador de eventos.

> [!IMPORTANT]
>  La función aparece en la tabla siguiente no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Espera a que un objeto que se señalice, mientras envía mensajes de ventana según sea necesario.|

## <a name="requirements"></a>Requisitos

**Encabezado:** atlbase.h

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop

Espera el objeto que se va a señalizar mientras envía mensajes de ventana según sea necesario.

> [!IMPORTANT]
>  Esta función no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Parámetros

*hEvent*<br/>
[in] El identificador de objeto que se va a esperar.

### <a name="return-value"></a>Valor devuelto

Devuelve TRUE si el objeto se haya señalado.

### <a name="remarks"></a>Comentarios

Esto es útil si desea esperar a suceder y recibir una notificación de lo que ocurre el evento de un objeto, pero permitir que los mensajes de ventana se distribuyan mientras espera.

## <a name="see-also"></a>Vea también

[Funciones](../../atl/reference/atl-functions.md)
