---
title: Habilitar información sobre herramientas | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 968d31b49c6d2b2fe5a5f69e04f58f17de8df5a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440490"
---
# <a name="enabling-tool-tips"></a>Habilitar la información sobre herramientas

Puede habilitar la compatibilidad con la sugerencia de herramienta para los controles secundarios de una ventana (por ejemplo, los controles de un cuadro de diálogo o la vista de formulario).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Para habilitar la información sobre herramientas para los controles secundarios de una ventana

1. Llame a `EnableToolTips` para la ventana para el que desea proporcionar información sobre herramientas.

1. Proporcionar una cadena para cada control en su [la notificación TTN_NEEDTEXT](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) controlador. El controlador está en el mapa de mensajes de la ventana que contiene los controles secundarios (por ejemplo, la clase de vista de formulario). Este controlador debe llamar a una función que identifica el control y establece **pszText** para especificar el texto utilizado por el control de información sobre herramientas.

## <a name="see-also"></a>Vea también

[Información sobre herramientas en ventanas no derivadas de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

