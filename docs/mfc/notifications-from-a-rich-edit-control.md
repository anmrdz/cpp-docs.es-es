---
title: Notificaciones de un amplio Control Edit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8898ac9d5aabebef42877ff063aaf93ceee77fad
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386805"
---
# <a name="notifications-from-a-rich-edit-control"></a>Notificaciones de un control Rich Edit

Informe de eventos que afectan a un amplio control de edición de los mensajes de notificación ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Pueden ser procesados por la ventana primaria o, mediante la reflexión de mensajes, mediante el amplio propio control de edición. Controles Rich edit admiten todos los mensajes de notificación utilizados con controles de edición, así como varias otras. Puede determinar qué mensajes de notificación de un control rich edit envía su ventana primaria estableciendo su "máscara de eventos".

Para establecer la máscara de eventos para un control rich edit, utilice la [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) función miembro. Puede recuperar la máscara de eventos actual para un control rich edit utilizando la [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) función miembro.

Los párrafos siguientes muestran varias notificaciones específicas y sus usos:

- EN_MSGFILTER Controlar la notificación EN_MSGFILTER permite una clase, ya sea el control rich edit o su ventana primaria, filtrar todos los teclado y mouse de entrada para el control. El controlador puede impedir que se está procesando el mensaje del teclado o mouse (ratón) o puede cambiar el mensaje modificando especificado [filtro de mensajes del](/windows/desktop/api/richedit/ns-richedit-_msgfilter) estructura.

- EN_PROTECTED controla el mensaje de notificación EN_PROTECTED para detectar cuando el usuario intenta modificar texto protegido. Para marcar un intervalo de texto como protegido, puede establecer el efecto de carácter protegido. Para obtener más información, consulte [formato de caracteres en los controles Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES se puede habilitar el usuario coloque los archivos en un control rich edit procesando el mensaje de notificación EN_DROPFILES. Especificado [ENDROPFILES](/windows/desktop/api/richedit/ns-richedit-_endropfiles) estructura contiene información acerca de los archivos que se va a quitar.

- EN_SELCHANGE aparecen en una aplicación puede detectar cuándo cambia la selección actual al procesar el mensaje de notificación EN_SELCHANGE aparecen. Especifica el mensaje de notificación un [SELCHANGE](/windows/desktop/api/richedit/ns-richedit-_selchange) estructura que contiene información sobre la nueva selección.

## <a name="see-also"></a>Vea también

[Uso de CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

