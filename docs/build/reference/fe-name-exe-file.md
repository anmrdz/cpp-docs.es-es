---
title: -Fe (nombre del archivo EXE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fe
dev_langs:
- C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad2683f79fdca845245fd266555e688aa8cf7374
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716240"
---
# <a name="fe-name-exe-file"></a>/Fe (Asignar nombre a un archivo ejecutable)

Especifica un nombre y un directorio para el archivo .exe o DLL creado por el compilador.

## <a name="syntax"></a>Sintaxis

> **/Fe**[_pathname_] **/Fe:** _pathname_

### <a name="arguments"></a>Argumentos

*ruta de acceso*<br/>
La ruta de acceso relativa o absoluta y nombre de archivo base o ruta de acceso relativa o absoluta a un directorio o un nombre de archivo base que se utilizará para el archivo ejecutable generado.

## <a name="remarks"></a>Comentarios

El **/Fe** opción le permite especificar el directorio de salida, nombre del archivo ejecutable de salida o ambos, para el archivo ejecutable generado. Si *pathname* termina con un separador de ruta de acceso (**&#92;**), se supone que especifique solo el directorio de salida. En caso contrario, el último componente de *pathname* se utiliza como el nombre base del archivo de salida y el resto de *pathname* especifica el directorio de salida. Si *pathname* no tiene los separadores de ruta de acceso, se supone que especifique el nombre de archivo de salida en el directorio actual. El *pathname* debe estar entre comillas dobles (**"**) si contiene todos los caracteres que no pueden estar en una ruta de acceso corta, como los espacios, caracteres o componentes de ruta de acceso más de ocho caracteres extendidos larga.

Cuando el **/Fe** opción no se especifica, o cuando un archivo de base no se especifica nombre *pathname*, el compilador proporciona el archivo de salida de un nombre predeterminado con el nombre base del primer archivo origen u objeto especificado en la línea de comandos y la extensión .exe o. dll.

Si especifica la [/c (compilar sin vincular)](c-compile-without-linking.md) opción, **/Fe** no tiene ningún efecto.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Abra el **propiedades de configuración** > **vinculador** > **General** página de propiedades.

1. Modificar el **archivo de salida** propiedad. Elija **Aceptar** para guardar los cambios.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Ejemplo

La siguiente línea de comandos compila y vincula todos los archivos de código fuente de C en el directorio actual. El archivo ejecutable resultante se denomina PROCESS.exe y se crea en el directorio "C:\Users\User Name\repos\My Project\bin".

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Ejemplo

La siguiente línea de comandos crea un archivo ejecutable en `C:\BIN` con el mismo nombre base que el primer archivo de origen en el directorio actual:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>Vea también

[/F (Opciones del archivo de resultados)](../../build/reference/output-file-f-options.md)<br/>
[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)<br/>
[Especificar la ruta de acceso](../../build/reference/specifying-the-pathname.md)<br/>
