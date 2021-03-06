---
title: Selección de varios controles | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- controls [C++], removing from groups
ms.assetid: efbdbade-0a3a-4328-b36e-a6376c06e8de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aec9785040f0a30150c8399b5059d6d733ad8be2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383838"
---
# <a name="selecting-multiple-controls"></a>Seleccionar varios controles

### <a name="to-select-multiple-controls"></a>Para seleccionar varios controles

1. En el [ventana cuadro de herramientas](/visualstudio/ide/reference/toolbox), seleccione el **puntero** herramienta.

2. Arrastre el puntero para dibujar un cuadro de selección alrededor de los controles que desea seleccionar en el cuadro de diálogo.

   Al soltar el botón del mouse, todos los controles internos y se selecciona el cuadro de selección de intersección.

   \- o -

- Mantenga presionada la **MAYÚS** clave y haga clic en los controles que le gustaría incluir en la selección.

   \- o -

- Mantenga presionada la **Ctrl** clave y haga clic en los controles que le gustaría incluir en la selección.

### <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>Para quitar un control de un grupo de controles seleccionados o para agregar un control a un grupo de controles seleccionados

1. Con un grupo de controles seleccionados, mantenga presionada la **MAYÚS** clave y haga clic en el control que desea quitar o agregar a la selección existente.

   > [!NOTE]
   > Manteniendo presionada la tecla el **Ctrl** clave y haga clic en un control dentro de una selección hará que controlan el control dominante en esa selección. Para obtener más información, consulte [especificar el Control dominante](../windows/specifying-the-dominant-control.md).

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Selección de controles](../windows/selecting-controls.md)<br/>
[Controles de cuadros de diálogo](../windows/controls-in-dialog-boxes.md)