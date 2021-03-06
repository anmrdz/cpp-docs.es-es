---
title: 'Windows Sockets: Derivar desde clases de Socket | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c562a8d6bf1c3f00f3812f6c25a4afd70276c64f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418962"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Sockets: Derivar de las clases de socket

Este artículo describe la funcionalidad que puede obtener al derivar su propia clase desde una de las clases de socket.

Puede derivar sus propias clases de socket desde [CAsyncSocket](../mfc/reference/casyncsocket-class.md) o [CSocket](../mfc/reference/csocket-class.md) para agregar su propia funcionalidad. En concreto, estas clases proporcionan una serie de funciones de miembro virtual que se pueden invalidar. Estas funciones incluyen [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), y [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Puede reemplazar las funciones de la clase socket derivada para aprovechar las ventajas de las notificaciones que se proporcionan cuando se producen eventos de red. El marco llama a estas funciones de devolución de llamada de notificación para avisarle de los eventos de socket importantes, como la recepción de datos que puede comenzar a leer. Para obtener más información acerca de las funciones de notificación, consulte [Windows Sockets: notificaciones de Socket](../mfc/windows-sockets-socket-notifications.md).

Además, la clase `CSocket` proporciona el [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) función miembro (un avanzado reemplazable). MFC llama a esta función, mientras que el socket suministra mensajes basados en Windows. Puede invalidar `OnMessagePending` para buscar mensajes concretos de Windows y responder a ellos.

La versión predeterminada de `OnMessagePending` incluida en la clase `CSocket` examina la cola de mensajes para mensajes WM_PAINT mientras se esperaba una llamada de bloqueo en completarse. Envía los mensajes de pintura para mejorar la calidad de la pantalla. Además de hacer algo útil, ilustra una forma de reemplazar la función por sí mismo. Como otro ejemplo, considere el uso de `OnMessagePending` para la tarea siguiente. Supongamos que muestra un cuadro de diálogo no modal mientras se espera que se complete una transacción red. El cuadro de diálogo contiene un botón de cancelación que el usuario puede utilizar para cancelar las transacciones de bloqueo que tardan demasiado tiempo. Su `OnMessagePending` invalidación podría suministrar mensajes relacionados con este cuadro de diálogo no modal.

En su `OnMessagePending` invalidar, devolver **TRUE** o el valor devuelto de una llamada a la versión de la clase base de `OnMessagePending`. Llame a la versión de la clase base si realiza el trabajo que desea realizada.

Para obtener más información, consulte:

- [Windows Sockets: Usar Sockets con archivos](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: Usar la clase CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: Bloquear](../mfc/windows-sockets-blocking.md)

- [Windows Sockets: Orden de bytes](../mfc/windows-sockets-byte-ordering.md)

- [Windows Sockets: Convertir cadenas](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Vea también

[Windows Sockets en MFC](../mfc/windows-sockets-in-mfc.md)

