---
title: 'Tutorial: Compilar un proyecto (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 09/14/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3071b779338150816cb1d52d16932ac0e3878538
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079329"
---
# <a name="walkthrough-building-a-project-c"></a>Tutorial: Compilar un proyecto (C++)

En este tutorial, va a introducir deliberadamente un error de sintaxis de Visual C++ en el código para obtener información acerca de cómo es un error de compilación y cómo corregirlo. Cuando compila el proyecto, un mensaje de error indica cuál es el problema y donde se produjo.

## <a name="prerequisites"></a>Requisitos previos

- En este tutorial se da por supuesto que conoce los fundamentos del lenguaje C++.

- También se presupone que ha completado los tutoriales relacionados anteriores que se enumeran en [Usar el IDE de Visual Studio para desarrollo de escritorio de C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

### <a name="to-fix-compilation-errors"></a>Para corregir errores de compilación

1. En Game.cpp, elimine el punto y coma de la última línea para que tenga un aspecto similar a la instrucción:

    `return 0`

1. En la barra de menús, elija **Compilar** > **Compilar solución**.

1. Un mensaje en la ventana **Lista de errores** indica que se produjo un error en la compilación del proyecto. La descripción se parecerá al mensaje de error:

    `error C2143: syntax error: missing ';' before '}'`

  Para ver la información de ayuda sobre este error, resáltelo en la ventana **Lista de errores** y después presione la tecla **F1**.

1. Vuelva a agregar el punto y coma al final de la línea que tiene el error de sintaxis:

   `return 0;`

1. En la barra de menús, elija **Compilar** > **Compilar solución**.

  Un mensaje en la ventana **Salida** indica que el proyecto se compiló correctamente.

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>Pasos siguientes

**Anterior:** [Tutorial: Trabajar con proyectos y soluciones (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**Siguiente:** [Tutorial: Probar un proyecto (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>

## <a name="see-also"></a>Vea también

[Referencia del lenguaje C++](../cpp/cpp-language-reference.md)<br/>
[Compilación de programas de C/C++](../build/building-c-cpp-programs.md)<br/>
