---
title: Crear un nuevo cuadro de diálogo (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fae55d0b4ce4a766952afcec7f78ec6b20fbb258
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426645"
---
# <a name="creating-a-new-dialog-box-c"></a>Crear un nuevo cuadro de diálogo (C++)

### <a name="to-create-a-new-dialog-box"></a>Para crear un nuevo cuadro de diálogo

1. En [vista de recursos](../windows/resource-view-window.md), haga clic en el archivo .rc y elija **Agregar recurso** en el menú contextual.

   > [!NOTE]
   > Si el proyecto no contuviera un archivo .rc, vea [Crear un nuevo archivo de script de recursos](../windows/how-to-create-a-resource-script-file.md).

2. En el **Agregar recurso** cuadro de diálogo, seleccione **diálogo** en el **tipo de recurso** lista y, después, haga clic en **New**.

   Si un signo más (**+**) aparece junto a la **diálogo** tipo de recurso, significa que están disponibles plantillas de cuadro de diálogo. Haga clic en el signo más para expandir la lista de plantillas, seleccione una plantilla y haga clic en **New**.

   Se abre el cuadro de diálogo nuevo en el **diálogo** editor.

   También puede [abrir cuadros de diálogo existentes en el editor de cuadro de diálogo para editar](../windows/viewing-and-editing-resources-in-a-resource-editor.md).

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Procedimiento para crear un recurso](../windows/how-to-create-a-resource.md)<br/>
[Archivos de recursos](../windows/resource-files-visual-studio.md)<br/>
[Editor de cuadros de diálogo](../windows/dialog-editor.md)