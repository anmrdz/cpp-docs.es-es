---
title: Importación y exportación | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc07ba1de15795e99a5e2ed75a5df9752026d08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717007"
---
# <a name="importing-and-exporting"></a>Importar y exportar

Puede importar símbolos públicos en una aplicación o exportar funciones desde un archivo DLL mediante dos métodos:

- Usar un archivo de módulo (.def) de definición al compilar el archivo DLL

- Usar las palabras clave **__declspec (dllimport)** o **__declspec (dllexport)** en una definición de función en la aplicación principal

## <a name="using-a-def-file"></a>Uso de un archivo .def

Un archivo de definición de módulo (.def) es un archivo de texto que contiene una o varias instrucciones de módulo que describen distintos atributos de un archivo DLL. Si no usas **__declspec (dllimport)** o **__declspec (dllexport)** requiere que un archivo .def para exportar funciones de un archivo DLL, el archivo DLL.

Puede usar los archivos .def para [importar a una aplicación](../build/importing-using-def-files.md) o a [exportar desde un archivo DLL](../build/exporting-from-a-dll-using-def-files.md).

## <a name="using-declspec"></a>Utilizar __declspec

Usos visuales C++ **__declspec (dllimport)** y **__declspec (dllexport)** para reemplazar el **__export** palabra clave que se había utilizado previamente en las versiones de 16 bits de Visual C++.

No es necesario usar **__declspec (dllimport)** para compilarse correctamente, pero si lo hace, el código permite que el compilador genere código de mejor calidad. El compilador es capaz de generar un código mejor, porque puede determinar si existe una función en un archivo DLL o no, que permite que el compilador genera código que omite un nivel de direccionamiento indirecto que normalmente estarían presente en una llamada de función que cruza un límite de DLL. Sin embargo, debe usar **__declspec (dllimport)** para importar las variables utilizadas en un archivo DLL.

Con la sección EXPORTS de archivo .def adecuado, **__declspec (dllexport)** no es necesario. **__declspec (dllexport)** se agregó para proporcionar una manera sencilla de exportar funciones desde un archivo .exe o .dll sin utilizar un archivo .def.

El formato de archivo Portable ejecutable Win32 está diseñado para minimizar el número de páginas que se debe tocar para corregir las importaciones. Para ello, coloca todas las direcciones de importación para cualquier programa en un lugar denominado tabla de direcciones de importación. Esto permite que el cargador modificar sólo una o dos páginas al tener acceso a estas importaciones.

## <a name="what-do-you-want-to-do"></a>¿Qué desea hacer?

- [Importar a una aplicación](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Exportar desde un archivo DLL](../build/exporting-from-a-dll.md)

## <a name="see-also"></a>Vea también

[Archivos DLL en Visual C++](../build/dlls-in-visual-cpp.md)