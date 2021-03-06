---
title: Personalizar o cambiar colores (Editor de imágenes para iconos) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
ms.assetid: e58f6b32-f435-4d9a-a570-7569433661ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e507942bbb0e6f77ec6423a51e4260f3fdd647a3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405195"
---
# <a name="customizing-or-changing-colors-image-editor-for-icons"></a>Personalizar o cambiar colores (Editor de imágenes para iconos)

El **imagen** del editor [paleta de colores](../windows/colors-window-image-editor-for-icons.md) muestra inicialmente los 16 colores estándar. Además de los colores mostrados, puede crear sus propios colores personalizados. A continuación, puede [guardar y cargar una paleta de colores personalizada](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md).

### <a name="to-change-colors-on-the-colors-palette"></a>Para cambiar los colores de la paleta de colores

1. Desde el **imagen** menú, elija **Ajustar colores**.

2. En el [cuadro de diálogo Selector de colores personalizados](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), defina el color escribiendo los valores RGB o HSL en los cuadros de texto correspondientes o elija un color en el **muestra de Color degradado** cuadro.

3. Establezca la luminosidad moviendo el control deslizante el **luminosidad** barra.

4. Muchos colores personalizados están interpolados. Si desea que el color sólido más próximo al color interpolado, haga doble clic en el **Color** cuadro.

   Si más adelante decide que desea el color interpolado, mueva el control deslizante el **luminosidad** barra o mueva la cruz el **muestra de Color degradado** cuadro de nuevo para restaurar la interpolación.

5. Haga clic en **Aceptar** para agregar el nuevo color.

## <a name="requirements"></a>Requisitos

Ninguna

## <a name="see-also"></a>Vea también

[Teclas de aceleración](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Trabajar con colores](../windows/working-with-color-image-editor-for-icons.md)