---
title: -bigobj (aumentar el número de secciones. Archivo obj) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bigobj
dev_langs:
- C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f10456bea8be552df42efe135818ac9c47393fc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721492"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Aumentar el número de secciones en el archivo .Obj)

**/bigobj** aumenta el número de secciones que puede contener un archivo de objeto.

## <a name="syntax"></a>Sintaxis

```
/bigobj
```

## <a name="remarks"></a>Comentarios

De manera predeterminada, un archivo objeto puede contener hasta 65.536 (2^16) secciones direccionables. Este es el caso independientemente de la plataforma de destino que se especifique. **/bigobj** incrementa esa capacidad de direccionamiento a 4.294.967.296 (2 ^ 32).

La mayoría de los módulos nunca generarán un archivo .obj que contenga más de 65.536 secciones. Sin embargo, un código generado por el equipo o un código que usa intensivamente las bibliotecas de plantillas puede requerir archivos .obj que puedan contener más secciones. **/ bigobj** está habilitada de forma predeterminada en los proyectos de plataforma Universal de Windows (UWP) porque el código XAML generado por la máquina incluye un gran número de encabezados. Si deshabilita esta opción en un proyecto de aplicación para UWP es probable que encuentre el error del compilador C1128.

Los vinculadores distribuidos antes de Visual C++ 2005 no pueden leer archivos .obj que se hayan generado con **/bigobj**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Haga clic en la carpeta **C/C++** .

1. Haga clic en la página de propiedades **Línea de comandos** .

1. Escriba la opción del compilador en el cuadro **Opciones adicionales** .

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)