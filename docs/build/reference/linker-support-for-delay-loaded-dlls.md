---
title: Compatibilidad del vinculador con las DLL de carga de retraso | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 555a46ee65a5d5d5565128a15af01a2c1cf18540
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711916"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Compatibilidad del vinculador con las DLL de carga retrasada

El vinculador de Visual C++ ahora admite la carga retrasada de DLL. Esto evita la necesidad de utilizar las funciones de Windows SDK **LoadLibrary** y **GetProcAddress** para implementar la carga retrasada de DLL.

Antes de Visual C++ 6.0, la única manera de cargar un archivo DLL en tiempo de ejecución era mediante **LoadLibrary** y **GetProcAddress**; el sistema operativo cargaba la DLL cuando el archivo ejecutable o DLL mediante archivos que se cargó.

A partir de Visual C++ 6.0, cuando se vinculan estáticamente con un archivo DLL, el vinculador proporciona opciones para retrasar cargar el archivo DLL hasta que el programa llama a una función en ese archivo DLL.

Una aplicación puede retrasar la carga de un archivo DLL mediante la [/DELAYLOAD (Retrasar importación de carga)](../../build/reference/delayload-delay-load-import.md) opción del vinculador con una función auxiliar (implementación de predeterminada proporcionada por Visual C++). La función auxiliar cargará el archivo DLL en tiempo de ejecución mediante una llamada a **LoadLibrary** y **GetProcAddress** para usted.

Debe considerar el retraso al cargar un archivo DLL si:

- El programa no puede llamar a una función en el archivo DLL.

- Es posible que se llama a una función en el archivo DLL hasta muy tarde en la ejecución del programa.

La carga retrasada de DLL se puede especificar durante la generación de una. EXE o. Proyecto DLL. UN OBJETO. Proyecto DLL que retrasa la carga de uno o más archivos DLL no debe propio llamar a un punto de entrada de carga retrasada de Dllmain.

Los temas siguientes describen la DLL de carga retrasada:

- [Especificar archivos DLL para carga retrasada](../../build/reference/specifying-dlls-to-delay-load.md)

- [Descargar explícitamente un archivo DLL de carga retrasada](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)

- [Cargar todas las importaciones para un archivo DLL de carga retrasada](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)

- [Enlazar importaciones](../../build/reference/binding-imports.md)

- [Notificación y control de errores](../../build/reference/error-handling-and-notification.md)

- [Volcar importaciones de carga retrasada](../../build/reference/dumping-delay-loaded-imports.md)

- [Restricciones de las DLL de carga retrasada](../../build/reference/constraints-of-delay-loading-dlls.md)

- [Descripción de la función auxiliar](understanding-the-helper-function.md)

- [Crear una función auxiliar personalizada](../../build/reference/developing-your-own-helper-function.md)

## <a name="see-also"></a>Vea también

[Archivos DLL en Visual C++](../../build/dlls-in-visual-cpp.md)<br/>
[Vinculación](../../build/reference/linking.md)