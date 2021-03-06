---
title: Cuadro de diálogo Herramienta de texto (C++) (Editor de imágenes para iconos) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.texttool
dev_langs:
- C++
helpviewer_keywords:
- text, adding to an image
- Text Tool dialog box [C++]
ms.assetid: a6036ef4-1871-40db-8239-6ddbe8f422f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55ad361c9252cfc4989926f90a9fedfd523c7d9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313456"
---
# <a name="text-tool-dialog-box-c-image-editor-for-icons"></a>Cuadro de diálogo Herramienta de texto (C++) (Editor de imágenes para iconos)

Use la **texto herramienta** cuadro de diálogo para agregar texto a un recurso de cursor, mapa de bits o icono.

Para obtener acceso a este cuadro de diálogo, abra el [Editor de imágenes](../windows/window-panes-image-editor-for-icons.md). Seleccione **herramientas** desde el **imagen** menú y, a continuación, seleccione el **texto herramienta** comando.

### <a name="font-button"></a>Botón de fuente

Se abre el [cuadro de diálogo fuente de herramienta de texto](../windows/text-tool-font-dialog-box-image-editor-for-icons.md), en el que puede cambiar la fuente, estilo o tamaño de la fuente del cursor. Los cambios se aplican al texto que se muestra en el **texto** área.

### <a name="text-area"></a>Área de texto

Muestra el texto que aparece como parte del recurso. Inicialmente, esta área está vacía.

> [!NOTE]
> Si **fondo transparente** está establecido, sólo el texto se colocará en la imagen. Si **fondo opaco** está establecido, un rectángulo delimitador, relleno con el [color de fondo](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), se colocarán detrás del texto. Para obtener más información, consulte [elegir opaco y fondos transparentes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Puede haga doble clic en el **texto herramienta** cuadro de diálogo para tener acceso a un menú contextual predeterminado que contiene una lista de comandos de Windows estándar.

## <a name="requirements"></a>Requisitos

Ninguna

## <a name="see-also"></a>Vea también

[Editar recursos gráficos](../windows/editing-graphical-resources-image-editor-for-icons.md)