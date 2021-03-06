---
title: Controlar la creación de la fecha y hora selector | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 864d6cfef599da61238baa92f7ab01a8ad82229d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393300"
---
# <a name="creating-the-date-and-time-picker-control"></a>Crear el control de selector de fecha y hora

¿Cómo se crea el control de selector de fecha y hora depende de si está utilizando el control en un cuadro de diálogo o crearla en una ventana nondialog.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>Usar CDateTimeCtrl directamente en un cuadro de diálogo

1. En el editor de cuadro de diálogo, agregar una fecha y el Control de selector de tiempo para el recurso de plantilla de cuadro de diálogo. Especifique su identificador de control.

1. Especifique cualquier estilo necesario, mediante el cuadro de diálogo Propiedades del control de selector de fecha y hora.

1. Use la [Asistente para agregar variables miembro](../ide/adding-a-member-variable-visual-cpp.md) para agregar una variable miembro de tipo [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) con la propiedad del Control. Este miembro puede utilizarse para llamar a `CDateTimeCtrl` funciones miembro.

1. Utilice la ventana Propiedades para asignar funciones de controlador en la clase de cuadro de diálogo para cualquier control de selector de fecha hora [notificación](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) mensajes que necesita para controlar (consulte [asignar mensajes a funciones](../mfc/reference/mapping-messages-to-functions.md)).

1. En [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), establecer los estilos adicionales para el `CDateTimeCtrl` objeto.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Usar CDateTimeCtrl en una ventana nondialog

1. Declare el control en la clase de vista o la ventana.

1. El control llama [crear](../mfc/reference/ctabctrl-class.md#create) función miembro, posiblemente en [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), posiblemente tan pronto como la ventana primaria [OnCreate](../mfc/reference/cwnd-class.md#oncreate) función de controlador (si es creación de subclases del control). Establecer los estilos para el control.

## <a name="see-also"></a>Vea también

[Uso de CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

