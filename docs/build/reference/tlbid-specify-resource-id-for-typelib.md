---
title: -TLBID (especificar Id. de recurso para una biblioteca de tipos) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e34e4d27c374fddd7710431e3a09f6a9ccfc802d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701319"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (Especificar un identificador de recursos para una biblioteca de tipos)

```
/TLBID:id
```

## <a name="arguments"></a>Argumentos

*identificador*<br/>
Un valor especificado por el usuario para una biblioteca de tipos creada por el vinculador. Invalida el identificador de recurso predeterminado de 1.

## <a name="remarks"></a>Comentarios

Cuando se compila un programa que utiliza atributos, el vinculador creará una biblioteca de tipos. El vinculador asignará un identificador de recurso de 1 a la biblioteca de tipos.

Si este identificador de recurso está en conflicto con uno de los recursos existentes, puede especificar otro identificador con /TLBID. El intervalo de valores que se pueden pasar a `id` es de 1 a 65535.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).

1. Haga clic en el **vinculador** carpeta.

1. Haga clic en el **IDL incrustado** página de propiedades.

1. Modificar el **Id. de recurso de TypeLib** propiedad.

### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación

1. Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Vea también

[Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opciones del vinculador](../../build/reference/linker-options.md)