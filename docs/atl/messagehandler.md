---
title: MessageHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0c7d76ff3b1e05d482b365150c9072a9fdd8d5c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076716"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` es el nombre de la función identificada por el segundo parámetro de la macro MESSAGE_HANDLER en el mapa de mensajes.

## <a name="syntax"></a>Sintaxis

```
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parámetros

*uMsg*<br/>
Especifica el mensaje.

*wParam*<br/>
Información adicional específica del mensaje.

*lParam*<br/>
Información adicional específica del mensaje.

*bHandled*<br/>
Los conjuntos de mapa de mensajes *bHandled* en TRUE antes de `MessageHandler` se llama. Si `MessageHandler` no controla totalmente el mensaje, se debe establecer *bHandled* en FALSE para indicar que el mensaje requiere un procesamiento posterior.

## <a name="return-value"></a>Valor devuelto

El resultado del procesamiento de mensajes. 0 si es correcto.

## <a name="remarks"></a>Comentarios

Para obtener un ejemplo del uso de este controlador de mensajes en un mapa de mensajes, vea [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Vea también

[Implementar una ventana](../atl/implementing-a-window.md)<br/>
[Mapas de mensajes](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
