---
title: -showIncludes (lista incluir archivos) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs:
- C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51305212f97482c6963ee2ba0d272c5c4692416e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709402"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (Enumerar archivos de inclusión)

Hace que el compilador genere una lista de los archivos de inclusión. Anidar incluyen archivos son también mostrados (archivos que se incluyen en los archivos que incluyen).

## <a name="syntax"></a>Sintaxis

```
/showIncludes
```

## <a name="remarks"></a>Comentarios

Cuando se encuentra un archivo de inclusión durante la compilación, un mensaje es la salida, por ejemplo:

```
Note: including file: d:\MyDir\include\stdio.h
```

Anidar incluyen los archivos se indican mediante una sangría, un espacio para cada nivel de anidamiento, por ejemplo:

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

En este caso, `2.h` incluyó desde dentro de `1.h`, por lo tanto, la sangría.

El **/showIncludes** opción emite a `stderr`, no `stdout`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Haga clic en la carpeta **C/C++** .

1. Haga clic en el **avanzadas** página de propiedades.

1. Modificar el **Mostrar inclusiones** propiedad.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)