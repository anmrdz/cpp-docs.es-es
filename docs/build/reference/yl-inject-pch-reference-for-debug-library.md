---
title: -Yl (Insertar referencia PCH para biblioteca de depuración) | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yl
dev_langs:
- C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 378d8e6b43a391c6d94c55b278bc71789981d9e3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712379"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Insertar referencia PCH para biblioteca de depuración)

El **/Yl** opción genera un único símbolo en un archivo de encabezado precompilado y se inserta una referencia a este símbolo en todos los archivos de objeto que usa el encabezado precompilado.

## <a name="syntax"></a>Sintaxis

>**/Yl**
> **/Yl**_nombre_
> **/Yl-**

### <a name="arguments"></a>Argumentos

*name*<br/>
Nombre opcional que se usa como parte del símbolo único.

*\-*<br/>
Deshabilita un guión (-) de forma explícita el **/Yl** opción del compilador.

## <a name="remarks"></a>Comentarios

El **/Yl** opción del compilador crea una definición de símbolo único en un archivo de encabezado precompilado creado mediante el uso de la [/Yc](../../build/reference/yc-create-precompiled-header-file.md) opción. Las referencias a este símbolo se insertan automáticamente en todos los archivos que incluyan el encabezado precompilado utilizando la [/Yu](../../build/reference/yu-use-precompiled-header-file.md) opción del compilador. El **/Yl** está habilitada de forma predeterminada cuando **/Yc** se usa para crear un archivo de encabezado precompilado.

El **/Yl**_nombre_ opción se utiliza para crear un símbolo de identificación en el archivo de encabezado precompilado. El compilador usa el *nombre* argumento como parte del nombre representativo del símbolo que crea, similar a `__@@_PchSym_@00@...@name`, donde la cadena de caracteres de un único generado por el compilador la representa de puntos suspensivos (...). Si el *nombre* argumento se omite, el compilador genera un nombre de símbolo automáticamente. Normalmente, no es necesario conocer el nombre del símbolo. Sin embargo, cuando el proyecto usa más de un archivo de encabezado precompilado, el **/Yl**_nombre_ opción puede resultar útil para determinar qué objeto de archivos de uso que el encabezado precompilado. Puede usar *nombre* como una cadena de búsqueda para buscar la referencia de símbolos en un archivo de volcado.

**/Yl-** deshabilita el comportamiento predeterminado y no se pone un símbolo de identificación en el archivo de encabezado precompilado. Archivos compilados que incluyen este encabezado precompilado no podrá obtener una referencia de símbolos comunes.

Cuando **/Yc** no se especifica, cualquier **/Yl** opción no tiene ningún efecto, pero si especificado debe coincidir con cualquier **/Yl** pasó cuando la opción **/Yc** es especificado.

Si usas **/Yl-**, **/Yc** y [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) opciones para generar un archivo de encabezado precompilado, la información de depuración se almacena en el archivo de objeto para el archivo de origen utilizado para crear el encabezado precompilado, en lugar de un archivo .pdb independiente. Si este archivo de objeto, a continuación, se realiza alguna parte de una biblioteca, [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) errores o [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) las advertencias pueden ocurrir en las compilaciones que usan esta biblioteca y el archivo de encabezado precompilado, si el archivo de origen utilizado para crear el archivo de encabezado precompilado no define ningún símbolo propio. El vinculador puede excluir el archivo objeto desde el vínculo, junto con la información de depuración asociada, cuando se hace referencia a nada en el archivo objeto en el cliente de la biblioteca. Para solucionar este problema, especifique **/Yl** (o quitar el **/Yl-** opción) cuando se usa **/Yc** para crear el archivo de encabezado precompilado. Esto garantiza que se vincula el archivo de objeto de la biblioteca que contiene la información de depuración en la compilación.

Para obtener más información sobre los encabezados precompilados, vea:

- [/Y (Encabezados precompilados)](../../build/reference/y-precompiled-headers.md)

- [Crear archivos de encabezado precompilados](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Seleccione el **propiedades de configuración** > **C o C++** > **línea de comandos** página de propiedades.

1. Agregar el **/Yl**_nombre_ opción del compilador en el **opciones adicionales** cuadro. Elija **Aceptar** para guardar los cambios.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)
