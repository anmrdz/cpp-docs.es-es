---
title: 'Servidores: Implementar Windows de marco en contexto | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6ef01a7943bbb0c14ec630651757a8665373b85
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055228"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Servidores: Implementar ventanas de marco en contexto

En este artículo se explica lo que debe hacer para implementar ventanas de marco en contexto en la aplicación de servidor de edición visual si no utiliza al Asistente para aplicaciones para crear la aplicación de servidor. En lugar de seguir el procedimiento descrito en este artículo, podría usar una clase de ventana de marco en contexto existente de una aplicación generada por el asistente o un ejemplo que se proporciona con Visual C++.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Para declarar una clase de ventana de marco en contexto

1. Derivar una clase de ventana de marco en contexto desde `COleIPFrameWnd`.

   - Utilice la macro DECLARE_DYNCREATE en el archivo de encabezado de clase.

   - Utilice la macro IMPLEMENT_DYNCREATE en el archivo de implementación (.cpp) de la clase. Esto permite que los objetos de esta clase que va a crear el marco de trabajo.

1. Declarar un `COleResizeBar` miembro en la clase de ventana de marco. Esto es necesario si desea admitir el cambio de tamaño en contexto en las aplicaciones de servidor.

   Declarar un `OnCreate` controlador de mensajes (mediante el **propiedades** ventana) y llamar a `Create` para su `COleResizeBar` miembro, si se ha definido.

1. Si tiene una barra de herramientas, declare un `CToolBar` miembro en la clase de ventana de marco.

   Invalidar el `OnCreateControlBars` función miembro para crear una barra de herramientas cuando el servidor está activo en su lugar. Por ejemplo:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   Vea la explicación de este código después del paso 5.

1. Incluir el archivo de encabezado para esta clase de ventana de marco en contexto en el archivo .cpp principal.

1. En `InitInstance` para la clase de aplicación, llame a la `SetServerInfo` función del objeto de plantilla de documento para especificar los recursos y la ventana de marco en contexto que se usará en abierto y en el contexto de edición.

Llama la serie de función el **si** instrucción crea la barra de herramientas de los recursos del servidor proporcionado. En este momento, la barra de herramientas es parte de la jerarquía de la ventana del contenedor. Dado que se deriva de esta barra de herramientas `CToolBar`, pasará sus mensajes a su propietario, la ventana de marco de la aplicación de contenedor, a menos que cambie el propietario. Por eso la llamada a `SetOwner` es necesario. Esta llamada cambia la ventana donde se envían los comandos de ventana de marco en contexto del servidor, la causa de los mensajes que se pasarán al servidor. Esto permite que el servidor reaccionar a las operaciones en la barra de herramientas que proporciona.

El identificador del mapa de bits de la barra de herramientas debe ser igual que los otros recursos en el contexto definidos en la aplicación de servidor. Consulte [menús y recursos: adiciones de servidor](../mfc/menus-and-resources-server-additions.md) para obtener más información.

Para obtener más información, consulte [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), y [CDocTemplate:: SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) en el *Class Library Reference*.

## <a name="see-also"></a>Vea también

[Servidores](../mfc/servers.md)<br/>
[Servidores: Implementar un servidor](../mfc/servers-implementing-a-server.md)<br/>
[Servidores: Implementar documentos de servidor](../mfc/servers-implementing-server-documents.md)<br/>
[Servidores: Elementos de servidor](../mfc/servers-server-items.md)

