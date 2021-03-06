---
title: Agregar un controlador de eventos (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd16628c48c30f6f554a842b70c5217753e305f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430311"
---
# <a name="adding-an-event-handler-visual-c"></a>Agregar un controlador de eventos (Visual C++)

Desde el editor de recursos, se puede agregar un controlador de eventos nuevo o modificar uno existente para un control de cuadro de diálogo mediante el [Asistente para controladores de eventos](../ide/event-handler-wizard.md).

Puede agregar un evento a la clase que implementa el cuadro de diálogo mediante la [ventana Propiedades](/visualstudio/ide/reference/properties-window). Si quiere agregar el evento a otra clase que no sea la del cuadro de diálogo, use al Asistente para controladores de eventos.

### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Para agregar un controlador de eventos a un control de cuadro de diálogo

1. Haga doble clic en el recurso de cuadro de diálogo en la [Vista de recursos](../windows/resource-view-window.md) para abrir el recurso de cuadro de diálogo que contiene el control en el [Editor de cuadros de diálogo](../windows/dialog-editor.md).

1. Haga clic con el botón derecho en el control para el que quiera controlar el evento de notificación.

1. En el menú contextual, haga clic en **Agregar controlador de eventos** para mostrar el Asistente para controladores de eventos.

1. Seleccione el evento en el cuadro **Tipo de mensaje** para agregar a la clase seleccionada en el cuadro **Lista de clases**.

1. Acepte el nombre predeterminado en el cuadro **Nombre del controlador de función** o proporcione uno de su elección.

1. Haga clic en **Agregar y editar** para agregar el controlador de eventos al proyecto y abrir el editor de texto por la función nueva para agregar el código del controlador de eventos apropiado.

   Si el tipo de mensaje seleccionado ya tiene un controlador de eventos para la clase seleccionada, **Agregar y editar** no estará disponible, y **Editar código** sí. Haga clic en **Editar código** para abrir el editor de texto por la función existente.

Como alternativa, puede agregar controladores de eventos desde la [ventana Propiedades](/visualstudio/ide/reference/properties-window). Vea [Adición de controladores de eventos para controles de cuadros de diálogo](../windows/adding-event-handlers-for-dialog-box-controls.md) para obtener más información.

## <a name="see-also"></a>Vea también

[Agregar funcionalidad con los Asistentes para código](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Agregar una clase](../ide/adding-a-class-visual-cpp.md)<br>
[Agregar una variable miembro](../ide/adding-a-member-variable-visual-cpp.md)<br>
[Agregar una función miembro](../ide/adding-a-member-function-visual-cpp.md)<br>
[Controlador de mensajes de MFC](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Navegar por la estructura de clases](../ide/navigating-the-class-structure-visual-cpp.md)