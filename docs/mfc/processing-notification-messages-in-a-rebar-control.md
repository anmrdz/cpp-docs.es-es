---
title: Procesar mensajes de notificación en un Control Rebar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4532206be5787266df470dedceda0880222b675f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438501"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Procesar mensajes de notificación en un control Rebar

En la clase primaria del control rebar, cree un `OnChildNotify` función de controlador con una instrucción switch para cualquier control rebar (`CReBarCtrl`) mensajes de notificación que desee controlar. Las notificaciones se envían a la ventana primaria cuando el usuario arrastra objetos sobre el control de rebar, cambia el diseño de las bandas rebar, elimina bandas del control rebar y así sucesivamente.

El objeto de control rebar pueden enviar los mensajes de notificación siguiente:

- RBN_AUTOSIZE se envía mediante un control rebar (creado con el estilo RBS_AUTOSIZE) cuando el control rebar cambia automáticamente de tamaño.

- RBN_BEGINDRAG se envía mediante un control rebar cuando el usuario comienza a arrastrar una banda.

- RBN_CHILDSIZE se envía mediante un control rebar cuando se cambia el tamaño de ventana secundaria de la de la banda.

- RBN_DELETEDBAND se envía mediante un control rebar después de que se ha eliminado una banda.

- RBN_DELETINGBAND se envía mediante un control rebar cuando una banda está a punto de eliminarse.

- RBN_BEGINDRAG se envía mediante un control rebar cuando el usuario deja de arrastrar una banda.

- RBN_GETOBJECT se envía mediante un control rebar (creado con el estilo RBS_REGISTERDROP) cuando se arrastra un objeto a través de una banda en el control.

- RBN_HEIGHTCHANGE se envía mediante un control rebar cuando ha cambiado su alto.

- RBN_LAYOUTCHANGED se envía mediante un control rebar cuando el usuario cambia el diseño de las bandas del control.

Para obtener más información sobre estas notificaciones, consulte [referencia del Control Rebar](https://msdn.microsoft.com/library/windows/desktop/bb774375) en el SDK de Windows.

## <a name="see-also"></a>Vea también

[Uso de CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

