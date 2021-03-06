---
title: Ver y agregar controles ActiveX a un cuadro de diálogo (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1eccaaff3f89b6353bd38e316ad515edc59eb9ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427412"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box-c"></a>Ver y agregar controles ActiveX a un cuadro de diálogo (C++)

Visual Studio le permite insertar controles ActiveX en el cuadro de diálogo.

### <a name="to-see-the-activex-controls-you-have-available"></a>Para ver los controles ActiveX que tiene a su disposición

1. Abra un cuadro de diálogo en el editor del cuadro de diálogo.

2. Haga clic en cualquier lugar del cuerpo del cuadro de diálogo.

3. En el menú contextual, haga clic en **Insertar control ActiveX**.

   Aparece el cuadro de diálogo [Insertar control ActiveX](../windows/insert-activex-control-dialog-box.md) y en él se muestran todos los controles ActiveX de su sistema. En la parte inferior del cuadro de diálogo, aparece la ruta de acceso al archivo del control ActiveX.

### <a name="to-add-an-activex-control-to-a-dialog-box"></a>Para agregar un control ActiveX a un cuadro de diálogo

1. En el cuadro de diálogo [Insertar control ActiveX](../windows/insert-activex-control-dialog-box.md), seleccione el control que quiera agregar al cuadro de diálogo y haga clic en **Aceptar**.

   El control aparece en el cuadro de diálogo, en el que puede editar o crear controladores para él como lo haría con cualquier otro control.

   > [!NOTE]
   > Puede agregar controles ActiveX a la [ventana del cuadro de herramientas](/visualstudio/ide/reference/toolbox).

   > [!CAUTION]
   > Puede que no sea legal distribuir todos los controles ActiveX en el sistema. Consulte el contrato de licencia para el software que instaló los controles o póngase en contacto con la compañía del software.

   Puede colocar controles en el **cuadro de herramientas** ventana para facilitar el acceso. Para obtener más información, vea [Cuadro de herramientas](/visualstudio/ide/reference/toolbox).

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Controles de cuadros de diálogo](../windows/controls-in-dialog-boxes.md)<br/>
[Controles ActiveX MFC](../mfc/mfc-activex-controls.md)<br/>
[Contenedores de controles ActiveX](../mfc/activex-control-containers.md)