---
title: Crear un objeto CToolBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98f99ef7ff26fed7d7df89881d2148af6bc993a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421653"
---
# <a name="creating-a-ctoolbarctrl-object"></a>Crear un objeto CToolBarCtrl

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) objetos contienen varias estructuras de datos interno: una lista de mapas de bits de imagen de botón, una lista de cadenas de la etiqueta de botón y una lista de `TBBUTTON` estructuras, que asocia una imagen o de cadena con la posición, el estilo, el estado, y Identificador de comando del botón. Cada uno de los elementos de estas estructuras de datos se denomina mediante un índice de base cero. Para poder usar un `CToolBarCtrl` de objeto, debe configurar estas estructuras de datos. Para obtener una lista de las estructuras de datos, vea [controles de barra de herramientas](controls-mfc.md) en el SDK de Windows. La lista de cadenas puede usarse solo para las etiquetas de botón; no se puede recuperar las cadenas de la barra de herramientas.

Para usar un `CToolBarCtrl` de objeto, normalmente se siguen estos pasos:

### <a name="to-use-a-ctoolbarctrl-object"></a>Para utilizar un objeto CToolBarCtrl

1. Construir la [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) objeto.

1. Llame a [crear](../mfc/reference/ctoolbarctrl-class.md#create) para crear el control común de barra de herramientas de Windows y adjuntarlo a la `CToolBarCtrl` objeto. Si desea que las imágenes de mapa de bits para los botones, agregar los mapas de bits de botón a la barra de herramientas mediante una llamada a [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Si desea que las etiquetas de cadena para los botones, agregue las cadenas a la barra de herramientas mediante una llamada a [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) o [a AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). Después de llamar a `AddString` o `AddStrings`, debe llamar a [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) con el fin de obtener la cadena o cadenas que aparezcan.

1. Agregar estructuras de botón a la barra de herramientas mediante una llamada a [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).

1. Si desea información sobre herramientas, controle **TTN_NEEDTEXT** mensajes en la ventana propietaria de la barra de herramientas, como se describe en [controlar herramienta notificaciones](../mfc/handling-tool-tip-notifications.md).

1. Si desea que el usuario pueda personalizar la barra de herramientas, controlar los mensajes de notificación de personalización en la ventana propietaria, como se describe en [controlar notificaciones de personalización](../mfc/handling-customization-notifications.md).

## <a name="see-also"></a>Vea también

[Uso de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

