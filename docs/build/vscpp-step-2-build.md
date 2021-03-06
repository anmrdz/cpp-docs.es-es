---
title: Compilar y ejecutar un proyecto de aplicación de consola de C++ | Microsoft Docs
description: Compilar y ejecutar una aplicación de consola Hola a todos en Visual C++
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- cpp-tools
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9c32f6811a18fae00cb2943a9ca97a89cf159a1
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029598"
---
# <a name="build-and-run-a-c-console-app-project"></a>Compilar y ejecutar un proyecto de aplicación de consola de C++

Cuando se crea un proyecto de aplicación de consola de C++ y se especificó el código, puede compilar y ejecutarla en Visual Studio y, a continuación, ejecutarlo como una aplicación independiente desde la línea de comandos.

## <a name="prerequisites"></a>Requisitos previos

- Hacer que Visual Studio con el desarrollo de escritorio con la carga de trabajo de C++ instalado y ejecutándose en el equipo. Si aún no está instalado, siga los pasos de [compatibilidad Install C++ en Visual Studio](../build/vscpp-step-0-installation.md).

- Crear un "Hello, World!" proyecto y escriba su código fuente. Si aún no lo ha hecho todavía, siga los pasos de [cree un proyecto de aplicación de consola C++](../build/vscpp-step-1-create.md).

Si Visual Studio tiene este aspecto, está listo para compilar y ejecutar la aplicación:

   ![Listo para crear el nuevo proyecto](../build/media/vscpp-ready-to-build.png "listo para compilar el proyecto nuevo")

## <a name="build-and-run-your-code-in-visual-studio"></a>Compilar y ejecutar el código en Visual Studio

1. Para compilar el proyecto, elija **compilar solución** desde el **compilar** menú. El **salida** ventana muestra los resultados del proceso de compilación.

   ![Compile el proyecto](../build/media/vscpp-build-solution.gif "compilar el proyecto")

1. Para ejecutar el código, en la barra de menús, elija **depurar**, **iniciar sin depurar**.

   ![Iniciar el proyecto](../build/media/vscpp-start-without-debugging.gif "iniciar el proyecto")

   Abre una ventana de consola y, a continuación, ejecuta la aplicación. Cuando se inicia una aplicación de consola en Visual Studio, ejecuta el código, a continuación, imprime "Presione cualquier tecla para continuar. . ." para ofrecerle la oportunidad de ver la salida.

¡Enhorabuena! Ha creado su primer "Hello, world!" ¡aplicación de consola en Visual Studio! Presione una tecla para cerrar la ventana de consola y vuelva a Visual Studio.

[Tenido un problema.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Ejecutar el código en una ventana de comandos

Normalmente, se ejecuta aplicaciones de consola en el símbolo del sistema, no en Visual Studio. Una vez compilada la aplicación mediante Visual Studio, puede ejecutarlo desde cualquier ventana de comandos. Aquí es cómo buscar y ejecutar la aplicación nueva en una ventana del símbolo del sistema.

1. En **el Explorador de soluciones**, seleccione la solución HelloWorld y haga doble clic para abrir el menú contextual. Elija **Abrir carpeta en el Explorador de archivos** para abrir un **Explorador de archivos** ventana en la carpeta de solución HelloWorld.

1. En el **Explorador de archivos** ventana, abra la carpeta de depuración. Este archivo contiene la aplicación, HelloWorld.exe y un par de otros archivos de depuración. Seleccione HelloWorld.exe, mantenga presionada la tecla MAYÚS y haga doble clic para abrir el menú contextual. Elija **copiar como ruta de acceso** para copiar la ruta de acceso a la aplicación en el Portapapeles.

1. Para abrir una ventana del símbolo del sistema, presione R de Windows para abrir el **ejecutar** cuadro de diálogo. Escriba *cmd.exe* en el **abierto** cuadro de texto, a continuación, elija **Aceptar** para ejecutar una ventana del símbolo del sistema.

1. En la ventana de símbolo del sistema, haga clic en para pegar la ruta de acceso a la aplicación en el símbolo del sistema. Presione ENTRAR para ejecutar la aplicación.

   ![Ejecute la aplicación en el símbolo](../build/media/vscpp-run-in-cmd.gif "ejecutar la aplicación en el símbolo del sistema")

Enhorabuena, ha compilado y ejecutar una aplicación de consola en Visual Studio.

[Tenido un problema.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Pasos siguientes

Una vez que ha creado y ejecutado esta sencilla aplicación, está listo para los proyectos más complejos. Consulte [mediante el IDE de Visual Studio para el desarrollo de escritorio de C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) para obtener más tutoriales que explican las capacidades de Visual C++ en Visual Studio.

## <a name="troubleshooting-guide"></a>Guía de solución de problemas

Venir aquí para las soluciones a problemas comunes al crear su primer proyecto de C++.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Compilar y ejecutar el código en problemas de Visual Studio

Si aparece un subrayado ondulado rojo bajo cualquier elemento en el editor de código fuente, la compilación puede tener errores o advertencias. Compruebe que el código coincide con el ejemplo de ortografía, puntuación y caso.

[Volver.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Ejecutar el código en una ventana de comandos de problemas

También puede navegar a la carpeta de depuración de la solución en la línea de comandos para ejecutar la aplicación. No se puede ejecutar la aplicación de otros directorios sin especificar la ruta de acceso a la aplicación. Sin embargo, puede copiar la aplicación en otro directorio y ejecutarlo desde allí.

Si no ve **copiar como ruta de acceso** en el menú contextual, descarte el menú y, a continuación, mantenga presionada la tecla MAYÚS mientras se vuelva a abrirlo. Esto es solo para su comodidad. También puede copiar la ruta de acceso a la carpeta de la barra de búsqueda del explorador de archivos y péguelo en el **ejecutar** cuadro de diálogo y, a continuación, escriba el nombre del archivo ejecutable al final. Es un poco más escritura, pero tiene el mismo resultado.

[Volver.](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
