---
title: Asignar mensajes a funciones | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b53175e46cfa858a73b581dfefc78047e96380d6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50058961"
---
# <a name="mapping-messages-to-functions"></a>Asignar mensajes a funciones

La ventana Propiedades permite enlazar controladores de mensajes (funciones miembro de clases de interfaz de usuario MFC) a los mensajes generados por los recursos de la aplicación. Usan [mapas de mensajes MFC](../../mfc/messages-and-commands-in-the-framework.md) para crear el enlace.

Cuando se usa la vista de clases para crear una nueva clase derivada de una de las clases de framework, lo automáticamente coloca un completo y funcional en el encabezado (. h) y la implementación (.cpp) los archivos de clases que especifique.

> [!NOTE]
>  Para agregar una nueva clase que no controla los mensajes, cree la clase directamente en el editor de texto.

### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Para definir o quitar un controlador de mensajes mediante la ventana Propiedades

1. En la Vista de clases, haga clic en la clase.

1. En la ventana Propiedades, haga clic en el **mensajes** botón.

    > [!NOTE]
    >  El **mensajes** botón está disponible cuando se selecciona el nombre de clase en la vista de clases o al hacer clic en la ventana de código fuente.

   Si el proyecto tiene un controlador para un mensaje, el nombre del controlador aparece en la columna derecha junto al mensaje.

1. Si el mensaje no tiene ningún controlador, a continuación, haga clic en la celda en la columna derecha en la ventana Propiedades para mostrar el nombre sugerido del controlador como \<Agregar >*HandlerName*. (Por ejemplo, el controlador de mensajes WM_TIMER sugiere \<Agregar >`OnTimer`).

1. Haga clic en el nombre sugerido para agregar código auxiliar para la función.

1. Para editar un controlador de mensajes, haga doble clic en el mensaje en la vista de clases y modificar el código en la ventana de código fuente.

Para quitar un controlador de mensajes, haga doble clic en el controlador en la columna derecha y seleccione \<eliminar >*HandlerName*. El código de la función se marca como comentario.

## <a name="see-also"></a>Vea también

[Controlador de mensajes de MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Agregar funcionalidad con los Asistentes para código](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Agregar una clase](../../ide/adding-a-class-visual-cpp.md)<br/>
[Agregar una función miembro](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Agregar una variable miembro](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Reemplazar una función virtual](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Agregar controladores de eventos para controles de cuadros de diálogo](../../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Navegar por la estructura de clases](../../ide/navigating-the-class-structure-visual-cpp.md)
