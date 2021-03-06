---
title: -DRIVER (controlador de modo Kernel de Windows NT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
dev_langs:
- C++
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae096c502cdc94d47a516caf4c29ac4f3eceb4b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705554"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Controlador de modo kernel de Windows NT)

>/ CONTROLADOR [: UPONLY |: WDM]

## <a name="remarks"></a>Comentarios

Use la **/DRIVER** opción del vinculador para compilar un controlador de modo kernel de Windows NT.

**UPONLY** hace que el vinculador agregue el **IMAGE_FILE_UP_SYSTEM_ONLY** a las características en el encabezado de salida para especificar que se trata de un controlador monoprocesador (UP). El sistema operativo se negará a cargar un controlador en un sistema multiprocesador (MP).

**/ Driver: WDM** hace que el vinculador establezca el **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** bit en el campo DllCharacteristics del encabezado opcional.

Si **/DRIVER** no se especifica, el vinculador no establece estos bits.

Si **/DRIVER** se especifica:

- **/ Fixed: no** está en vigor. Para obtener más información, consulte [/FIXED (Dirección base fija)](../../build/reference/fixed-fixed-base-address.md).

- La extensión del archivo de salida se establece en .sys. Use **/OUT** para cambiar el nombre de archivo predeterminado y la extensión. Para obtener más información, consulte [/OUT (Nombre del archivo de salida)](../../build/reference/out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).

1. Haga clic en el **vinculador** carpeta.

1. Haga clic en el **sistema** página de propiedades.

1. Modificar el **controlador** propiedad.

### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación

- Consulte [VCLinkerTool.driver propiedad](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Vea también

[Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opciones del vinculador](../../build/reference/linker-options.md)
