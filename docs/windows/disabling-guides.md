---
title: Deshabilitar guías | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- guides, disabling snapping
- Dialog editor [C++], snap to guides
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
ms.assetid: 51efa07b-8684-474e-a0b4-191ec5d91d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35c552a6bb384f87c358ba25a945a7f02cc30114
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380807"
---
# <a name="disabling-guides"></a>Deshabilitar guías

Puede usar las teclas especiales junto con el mouse para deshabilitar el efecto de las guías de ajuste. Mediante el **Alt** clave deshabilita los efectos de ajuste de la Guía seleccionada. Mover una guía con el **MAYÚS** clave impide que los controles ajustados mover con la guía.

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>Para deshabilitar el efecto de ajuste de las guías

1. Arrastre el control mientras mantiene presionada la **Alt** clave.

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Para mover guías sin mover los controles ajustados

1. Arrastre la guía mientras mantiene presionada la **MAYÚS** clave.

### <a name="to-turn-off-the-guides"></a>Para desactivar las guías

1. Desde el **formato** menú, elija **configuración de la guía**.

2. En el [cuadro de diálogo de configuración de guía](../windows/guide-settings-dialog-box.md), en **las guías de diseño**, seleccione **ninguno**.

   > [!NOTE]
   > También puede haga doble clic en la barra de la regla para tener acceso a la **configuración de la guía** cuadro de diálogo.

\- o -

- En el **formato** menú, haga clic en **Alternar guías**.

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Estados del Editor de cuadros de diálogo (guías y cuadrículas)](../windows/dialog-editor-states-guides-and-grids.md)<br/>
[Controles de cuadros de diálogo](../windows/controls-in-dialog-boxes.md)