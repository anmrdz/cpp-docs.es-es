---
title: Usar controles de árbol | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc3efbf48a9005bf117c2dd7ab5f1bd01ed556d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403687"
---
# <a name="using-tree-controls"></a>Usar controles de árbol

Uso típico de un control de árbol ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sigue el patrón siguiente:

- Se crea el control. Si el control se especifica en una plantilla de cuadro de diálogo o si usa `CTreeView`, creación es automática cuando se crea el cuadro de diálogo o la vista. Si desea crear el control de árbol como una ventana secundaria de alguna otra ventana, utilice el [crear](../mfc/reference/ctreectrl-class.md#create) función miembro.

- Si desea que el control de árbol para usar imágenes, establezca una lista de imágenes mediante una llamada a [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist). También puede cambiar la sangría llamando [SetIndent](../mfc/reference/ctreectrl-class.md#setindent). Es un buen momento para hacer esto en [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (para los controles de cuadros de diálogo) o [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (para las vistas).

- Colocar datos en el control mediante una llamada a la `CTreeCtrl`del [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) función una vez para cada elemento de datos. `InsertItem` Devuelve un identificador para el elemento que se puede usar para hacer referencia a él más adelante, por ejemplo, cuando se agregan elementos secundarios. Es un buen momento para inicializar los datos en `OnInitDialog` (para los controles de cuadros de diálogo) o `OnInitialUpdate` (para las vistas).

- Cuando el usuario interactúa con el control, enviará varios mensajes de notificación. Puede especificar una función para controlar cada uno de los mensajes que desea administrar mediante la adición de una macro ON_NOTIFY_REFLECT en mapa de mensajes de la ventana de control o mediante la adición de una macro ON_NOTIFY al mapa de mensajes de la ventana primaria. Consulte [mensajes de notificación de Control de árbol](../mfc/tree-control-notification-messages.md) más adelante en este tema para obtener una lista de las notificaciones posibles.

- Llamar a las distintas funciones de miembro Set para establecer valores para el control. Los cambios que puede realizar incluyen establecer la sangría y cambiar el texto, imágenes o datos asociados a un elemento.

- Use las distintas funciones Get para examinar el contenido del control. También puede recorrer el contenido del control de árbol con funciones que permiten recuperar identificadores de elementos primarios, secundarios y relacionados de un elemento especificado. Incluso puede ordenar a los elementos secundarios de un nodo determinado.

- Cuando haya terminado con el control, asegúrese de que se destruya correctamente. Si el control de árbol está en un cuadro de diálogo o si se trata de una vista, lo y `CTreeCtrl` automáticamente se destruirá el objeto. Si no, deberá asegurarse de que el control y la `CTreeCtrl` objeto se destruyan correctamente.

## <a name="see-also"></a>Vea también

[Uso de CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

