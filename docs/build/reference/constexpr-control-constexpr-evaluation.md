---
title: -constexpr (controlar la evaluación constexpr) | Microsoft Docs
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /constexpr
- -constexpr
dev_langs:
- C++
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 462690a2b237d08adb9b16a68d38ad5258e958e2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703747"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (controlar la evaluación constexpr)

Use la **/constexpr** opciones del compilador para los parámetros de control para **constexpr** evaluación en tiempo de compilación.

## <a name="syntax"></a>Sintaxis

> **/ constexpr: Depth**<em>N</em>
>  **/constexpr: backtrace**<em>N</em>
>  ** /constexpr: Steps** <em>N</em>

## <a name="arguments"></a>Argumentos

**profundidad**<em>N</em> limitar la profundidad de recursiva **constexpr** invocación de función *N* niveles. El valor predeterminado es 512.

**seguimiento regresivo**<em>N</em> mostrar hasta *N* **constexpr** evaluaciones en diagnósticos. El valor predeterminado es 10.

**pasos**<em>N</em> Terminate **constexpr** evaluación después *N* pasos. El valor predeterminado es 100.000.

## <a name="remarks"></a>Comentarios

El **/constexpr** opciones del compilador de controlan la evaluación de tiempo de compilación de **constexpr** expresiones. Pasos para la evaluación, los niveles de recursividad y seguimiento regresivo profundidad se controlan para evitar que el compilador dedicar demasiado tiempo en **constexpr** evaluación. Para obtener más información sobre la **constexpr** elemento del lenguaje, consulte [constexpr (C++)](../../cpp/constexpr-cpp.md).

El **/constexpr** opciones están disponibles a partir de Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el proyecto **páginas de propiedades** cuadro de diálogo.

2. En **propiedades de configuración**, expanda el **C o C++** carpeta y elija el **línea de comandos** página de propiedades.

3. Escriba cualquier **/constexpr** opciones del compilador en el **opciones adicionales** cuadro. Elija **Aceptar** o **aplicar** para guardar los cambios.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)