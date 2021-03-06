---
title: 'Nuevo proyecto a partir de código existente: configuración de depuración (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.debugsettings
dev_langs:
- C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df50dfba79ad4160728e77b96d5814d6b03add1e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440895"
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Especifique los valores de configuración de Debug, Asistente para crear nuevo proyecto de archivos de código fuente existentes.

Use esta página del Asistente para crear nuevos proyectos a partir de archivos de código fuente existentes para especificar los valores del proyecto de configuración de depuración.

## <a name="task-list"></a>Lista de tareas

[Cómo: Crear un proyecto de C++ a partir del código existente](../ide/how-to-create-a-cpp-project-from-existing-code.md)

## <a name="uielement-list"></a>Lista de UIElement

- **Línea de comandos de Compilar**

   Especifica la línea de comandos que compila el proyecto nuevo. Por ejemplo, escriba el nombre del compilador (además de los modificadores y argumentos) o los scripts de compilación que quiera usar para compilar el proyecto nuevo. Esta opción está habilitada si se selecciona la opción **Usar el sistema de compilación externo** en la página **Especificar configuración de proyecto**; en caso contrario, no está disponible.

- **Línea de comandos de recompilación**

   Especifica la línea de comandos que recompila el proyecto nuevo. Esta opción está habilitada si se selecciona la opción **Usar el sistema de compilación externo** en la página **Especificar configuración de proyecto**; en caso contrario, no está disponible.

- **Línea de comandos de limpieza**

   Especifica la línea de comandos para eliminar los archivos de soporte generados por las herramientas de compilación para el proyecto nuevo. Esta opción está habilitada si se selecciona la opción **Usar el sistema de compilación externo** en la página **Especificar configuración de proyecto**; en caso contrario, no está disponible.

- **Salida (para depuración)**

   Especifica la ruta de acceso del directorio de los archivos de salida para la configuración de depuración del proyecto nuevo. Esta opción está habilitada si se selecciona la opción **Usar el sistema de compilación externo** en la página **Especificar configuración de proyecto**; en caso contrario, no está disponible.

- **Definiciones del preprocesador (/D)**

   Define símbolos de preprocesador para el proyecto nuevo. Para obtener más información, vea [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).

- **Ruta de acceso de búsqueda de inclusión (/I)**

   Especifica las rutas de acceso de directorio para agregar a la lista de directorios que el compilador debe buscar para resolver las referencias de archivo que se pasan a las directivas de preprocesador en el proyecto nuevo. Para obtener más información, consulte [/I (Directorios de inclusión adicionales)](../build/reference/i-additional-include-directories.md).

- **Archivos de inclusión forzados (/FI)**

   Especifica los archivos de encabezado que se van a procesar al compilar el proyecto nuevo. Para obtener más información, consulte [/FI (Dar nombre al archivo de inclusión forzado)](../build/reference/fi-name-forced-include-file.md).

- **Ruta de acceso de búsqueda de ensamblado .NET (/AI)**

   Especifica las rutas de acceso de directorio que el compilador debe buscar para resolver las referencias de ensamblado .NET que se pasan a las directivas de preprocesador en el proyecto nuevo. Para obtener más información, consulte [/AI (Especificar directorios de metadatos)](../build/reference/ai-specify-metadata-directories.md).

- **Forzados usando ensamblados .NET (/FU)**

   Especifica los ensamblados .NET que se van a procesar al compilar el proyecto nuevo. Para obtener más información, consulte [/FU (Dar nombre al archivo #using forzado)](../build/reference/fu-name-forced-hash-using-file.md).

## <a name="see-also"></a>Vea también

[Especificar configuración de proyecto, Asistente para crear nuevo proyecto de archivos de código fuente existentes](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)
