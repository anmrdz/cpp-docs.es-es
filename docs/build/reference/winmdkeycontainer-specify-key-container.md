---
title: -WINMDKEYCONTAINER (especificar contenedor de claves) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs:
- C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d48a0966b974b1a264b4d2b539f5861ce0dfd57
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716831"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (Especificar contenedor de claves)

Especifica un contenedor de claves para firmar un archivo de metadatos de Windows (.winmd).

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Comentarios

Es similar a la [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) opción del vinculador que se aplica a un archivo (.winmd).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Seleccione el **vinculador** carpeta.

1. Seleccione el **Windows metadatos** página de propiedades.

1. En el **contenedor de claves de metadatos de Windows** , escriba la ubicación.

## <a name="see-also"></a>Vea también

[Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opciones del vinculador](../../build/reference/linker-options.md)