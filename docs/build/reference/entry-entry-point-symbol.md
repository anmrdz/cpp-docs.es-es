---
title: -ENTRY (símbolo de punto de entrada) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
dev_langs:
- C++
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f5a18b061cbd956731ced6788e86f871ea97bd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719581"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (Símbolo de punto de entrada)

```
/ENTRY:function
```

## <a name="arguments"></a>Argumentos

*function*<br/>
Dirección de una función que especifica un inicio definido por el usuario para un archivo .exe o DLL.

## <a name="remarks"></a>Comentarios

La opción /ENTRY especifica una función de punto de entrada como dirección inicial para un archivo .exe o DLL.

La función debe definirse para usar el `__stdcall` convención de llamada. Los parámetros y el valor devuelto dependen de si el programa es una aplicación de consola, una aplicación de windows o un archivo DLL. Se recomienda permitir que el vinculador establezca el punto de entrada para que la biblioteca de tiempo de ejecución de C se inicializa correctamente y se ejecutan los constructores de C++ para objetos estáticos.

De forma predeterminada, la dirección de inicio es un nombre de función de la biblioteca de tiempo de ejecución de C. El vinculador selecciona según los atributos del programa, como se muestra en la tabla siguiente.

|Nombre de la función|Valor predeterminado para|
|-------------------|-----------------|
|**mainCRTStartup** (o **wmainCRTStartup**)|Una aplicación que utilice/SUBSYSTEM: Console; las llamadas `main` (o `wmain`)|
|**WinMainCRTStartup** (o **wWinMainCRTStartup**)|Una aplicación que utilice/SUBSYSTEM:**WINDOWS**; llamadas `WinMain` (o `wWinMain`), que debe definirse para usar `__stdcall`|
|**_DllMainCRTStartup**|UN ARCHIVO DLL; las llamadas `DllMain` si existe, que debe definirse para usar `__stdcall`|

Si el [/DLL](../../build/reference/dll-build-a-dll.md) o [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) opción no se especifica, el vinculador selecciona un punto de entrada y el subsistema dependiendo de si `main` o `WinMain` está definido.

Las funciones `main`, `WinMain`, y `DllMain` son las tres formas de punto de entrada definido por el usuario.

Al crear una imagen administrada, la función especificada a/Entry debe tener una firma de (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).

Para obtener información sobre cómo definir las suyas propias `DllMain` punto de entrada, consulte [archivos DLL y Visual C++ comportamiento de la biblioteca de tiempo de ejecución](../../build/run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).

1. Haga clic en el **vinculador** carpeta.

1. Haga clic en el **avanzadas** página de propiedades.

1. Modificar el **punto de entrada** propiedad.

### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>Vea también

[Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opciones del vinculador](../../build/reference/linker-options.md)