---
title: Cómo notificar un problema con el conjunto de herramientas de Visual C++ | Microsoft Docs
ms.date: 06/21/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2ca0f4aa5f3965adc97e4cdaef09e01646e8809
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062124"
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset-or-documentation"></a>Cómo notificar un problema con la documentación o el conjunto de herramientas de Visual C++

Si tiene problemas con el Compilador de Microsoft Visual C++, el enlazador u otras herramientas y bibliotecas de Visual C++, nos gustaría que nos informara de ello. Si el problema está en la documentación, también queremos estar al tanto.

## <a name="how-to-report-a-c-toolset-issue"></a>Cómo informar de un problema del conjunto de herramientas de C++

La mejor manera de comunicarnos un problema consiste en enviarnos un informe que incluya una descripción del problema que ha encontrado, detalles sobre cómo está compilando el programa y una *reproducción*, un caso de prueba completo que podamos usar para reproducir el problema en nuestras máquinas. Esta información nos permite comprobar rápidamente que el problema está en nuestro código y que no es local de su entorno para determinar si afecta a otras versiones del compilador y diagnosticar la causa.

En las siguientes secciones, verá qué es lo que hace que un informe sea bueno, cómo generar una reproducción del tipo de problema que ha detectado y cómo enviar el informe al equipo del producto. Sus informes son importantes para nosotros y para otros desarrolladores como usted. Gracias por ayudarnos a mejorar Visual C++.

## <a name="how-to-prepare-your-report"></a>Cómo preparar un informe

Es importante crear un informe de alta calidad, ya que resulta muy difícil reproducir el problema que ha encontrado en la máquina si no aporta información completa. Cuanto mejor sea su informe, más eficazmente podremos recrear y diagnosticar el problema.

Como mínimo, el informe debe contener lo siguiente:

- Información de versión completa sobre el conjunto de herramientas que está usando.

- La línea de comandos cl.exe completa usada para compilar el código.

- Una descripción detallada del problema que se ha encontrado.

- Una reproducción es un ejemplo de código fuente completo, simplificado y autocontenido en el que se muestra el problema en cuestión.

Siga leyendo para conocer qué información específica necesitamos, dónde puede encontrarla y cómo puede crear una reproducción correcta.

### <a name="the-toolset-version"></a>La versión del conjunto de herramientas

Necesitamos la información de versión completa y la arquitectura de destino del conjunto de herramientas que causa el problema para poder probar la reproducción que nos facilite con el mismo conjunto de herramientas en nuestras máquinas. Si podemos reproducir el problema, esta información también nos dará un punto de partida para investigar en qué otras versiones del conjunto de herramientas se produce el mismo problema.

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>Para informar sobre la versión completa del compilador que está usando

1. Abra el **símbolo del sistema para desarrolladores** que coincida con la arquitectura de configuración y la versión de Visual Studio utilizadas para compilar su proyecto. Por ejemplo, si crea una compilación usando Visual Studio 2017 en x64 para destinos x64, elija el **símbolo del sistema de las herramientas nativas x64 para VS 2017**. Para obtener más información, vea [Developer command prompt shortcuts](build/building-on-the-command-line.md#developer-command-prompt-shortcuts) (Accesos directos al símbolo del sistema para desarrolladores).

1. En la ventana de la consola del símbolo del sistema para desarrolladores, escriba el comando **cl /Bv**.

La salida debe tener un aspecto similar a este:

```Output
C:\Users\username\Source>cl /Bv
Microsoft (R) C/C++ Optimizing Compiler Version 19.14.26428.1 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

Compiler Passes:
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\cl.exe:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1xx.dll:      Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c2.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\link.exe:      Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\mspdb140.dll:  Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\1033\clui.dll: Version 19.14.26428.1

cl : Command line error D8003 : missing source filename
```

Copie y pegue toda la salida en el informe.

### <a name="the-command-line"></a>La línea de comandos

Necesitamos la línea de comandos exacta (cl.exe y todos sus argumentos) que se ha usado en la compilación del código para poder compilarlo exactamente del mismo modo en nuestras máquinas. Esto es importante porque el problema que se ha encontrado podría existir únicamente al compilar con un argumento determinado o con una combinación de argumentos determinada.

El mejor lugar para encontrar esta información es el registro de compilación inmediatamente después de experimentar el problema. Esto garantiza que la línea de comandos contiene exactamente los mismos argumentos que podrían contribuir al problema.

#### <a name="to-report-the-contents-of-the-command-line"></a>Para informar sobre el contenido de la línea de comandos

1. Busque el archivo **CL.command.1.tlog** y ábralo. De forma predeterminada, este archivo se encuentra en la carpeta Documentos, en \\Visual Studio *versión*\\Projects\\*SolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*.tlog\\CL.command.1.tlog, o bien en la carpeta Usuario, en \\Source\\Repos\\*SolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*.tlog\\CL.command.1.tlog. Es posible que se encuentre en otra ubicación si utiliza otro sistema de compilación o ha modificado la ubicación predeterminada de su proyecto.

   En este archivo, encontrará los nombres de los archivos de código fuente seguidos de los argumentos de la línea de comandos que se han usado para compilarlos, cada uno en líneas independientes.

1. Busque la línea que contenga el nombre del archivo de código fuente donde se produce el problema. La línea inferior contiene los argumentos del comando cl.exe correspondiente.

Copie y pegue toda la línea de comandos en el informe.

### <a name="a-description-of-the-problem"></a>Una descripción del problema

Necesitamos una descripción detallada del problema que se ha encontrado para que podamos comprobar que tiene el mismo efecto en nuestras máquinas. Además, a veces también nos ayuda saber qué estaba intentando conseguir y qué esperaba que sucediera.

Indique los **mensajes de error exactos** enviados por el conjunto de herramientas o el comportamiento en tiempo de ejecución exacto que observe. Necesitamos esta información para comprobar que hayamos reproducido el problema correctamente. Incluya **toda** la salida del compilador, no solo el último mensaje de error. Tenemos que ver todos los elementos que han provocado el problema del que nos informe. Si puede duplicar el problema usando el compilador de la línea de comandos, es preferible que nos envíe esa salida del compilador. El IDE y otros sistemas de compilación podrían filtrar los mensajes de error que se le hayan devuelto o bien registrar solo la primera línea de un mensaje de error.

Si el problema es que el compilador acepta código no válido y no genera ningún diagnóstico, anótelo en el informe.

Para informar de un problema de comportamiento en tiempo de ejecución, incluya una **copia exacta** de lo que el programa imprime y de lo que espera ver. Idealmente, se inserta en la propia instrucción de salida, por ejemplo, `printf("This should be 5: %d\n", actual_result);`. Si el programa se bloquea o deja de responder, menciónelo también.

Agregue cualquier otra información que nos pueda ayudar a diagnosticar el problema que ha experimentado, por ejemplo, una solución alternativa que haya encontrado. Evite repetir la información que se encuentra en otro lugar del informe.

### <a name="the-repro"></a>La reproducción

Una reproducción es un ejemplo de código fuente autocontenido y completo que muestra el problema que se ha detectado de forma reproducible, de ahí su nombre. Necesitamos una reproducción para poder reproducir el error en nuestros equipos. El código debería ser suficiente para crear un ejecutable simple que permita la compilación y la ejecución, o bien que las permitiera si no fuese por el problema que ha detectado. Las reproducciones no son fragmentos de código: deben tener funciones y clases completas y, además, contener todas las directivas #include necesarias, incluso en el caso de los encabezados estándares.

#### <a name="what-makes-a-good-repro"></a>Características de una reproducción adecuada

A continuación encontrará lo que se considera una buena reproducción:

- **Es mínima.** Las reproducciones deben ser lo más pequeñas posible, pero mostrar exactamente el problema detectado. No es necesario que sean complejas o realistas, sino que solo deben mostrar código que cumpla con el estándar o la implementación del compilador documentada. O bien, en el caso de que falte un diagnóstico, el código que no sea conforme. Las reproducciones simples y concisas que contienen suficiente código para mostrar el problema son las mejores. Si puede eliminar o simplificar el código de forma que siga siendo conforme y dejar, a la vez, el problema sin cambios, también puede hacerlo. No es necesario incluir contraejemplos del código que funciona.

- **Es autocontenida.** Las reproducciones deben evitar las dependencias innecesarias. Si puede reproducir el problema sin bibliotecas de terceros, hágalo. Si puede reproducir el problema sin código de biblioteca, además de proporcionar instrucciones de salida simples (por ejemplo, si `puts("this shouldn't compile");`, `std::cout << value;` y `printf("%d\n", value);` funcionan), hágalo. La mejor opción es condensar un ejemplo en un único archivo de código fuente sin hacer referencia a ningún encabezado de usuario. Nos resulta extremadamente útil que reduzca la cantidad de código que debemos tener en cuenta como posible causante del problema.

- **Tiene la versión más reciente del compilador.** Cuando sea posible, las reproducciones deben usar la actualización más reciente a la última versión del conjunto de herramientas, o bien la versión preliminar más reciente de la siguiente actualización o de la siguiente versión principal. Muy a menudo, los problemas que se pueden producir en versiones anteriores del conjunto de herramientas se han corregido en las versiones más recientes. Las correcciones se trasladan a las versiones anteriores solo en circunstancias excepcionales.

- Si procede, **conviene realizar comprobaciones con otros compiladores**. Las reproducciones que implican código C++ portátil deben comprobar su comportamiento con otros compiladores si es posible. En última instancia, el estándar determina la corrección de un programa. Ningún compilador es perfecto, aunque cuando Clang y GCC acepten su código sin diagnóstico y MSVC no lo haga, es probable que se trate de un error en el compilador. Existen otras posibilidades, como las diferencias entre el comportamiento de Unix y Windows o los distintos niveles de implementación de los estándares de C++, entre otras. Por otra parte, si todos los compiladores rechazan su código, es probable que este no sea correcto. Consultar distintos mensajes de error puede ayudarle a diagnosticar el problema.

   Encontrará listas de compiladores en línea para probar su código en los [compiladores en línea de C++](https://isocpp.org/blog/2013/01/online-c-compilers) del sitio web del estándar ISO C++, o bien en esta [lista de compiladores en línea de C++](https://arnemertz.github.io/online-compilers/) de GitHub. Algunos ejemplos específicos son [Wandbox](https://wandbox.org/), [Compiler Explorer](https://godbolt.org/) y [Coliru](http://coliru.stacked-crooked.com/).

   > [!NOTE]
   > Los sitios web de compiladores en línea no están afiliados a Microsoft. Muchos de estos sitios web de compiladores en línea se ejecutan como proyectos personales, y puede que algunos de ellos no estén disponibles cuando lea este artículo. Haga una búsqueda para encontrar otros que pueda usar.

Los problemas que se producen en compiladores, enlazadores o bibliotecas suelen mostrarse de una forma particular. El tipo de problema que ha experimentado determinará el tipo de reproducción que debe incluir en el informe. Sin una reproducción adecuada, no tenemos nada para investigar. Aquí encontrará algunos de los tipos de problemas que puede detectar, así como las instrucciones para generar los tipos de reproducciones que debe utilizar para informar de cada uno de los problemas.

#### <a name="frontend-parser-crash"></a>Bloqueo de front-end (analizador)

Los bloqueos de front-end se producen durante la fase de análisis del compilador. Normalmente, el compilador emitirá el mensaje [Error irrecuperable C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) y hará referencia al archivo de código fuente y al número de línea en el que se produjo el error. A menudo mencionará un archivo msc1.cpp, pero puede pasar por alto este detalle.

Para este tipo de bloqueo, proporcione una [reproducción preprocesada](#preprocessed-repros).

A continuación se muestra un ejemplo de la salida del compilador para este tipo de bloqueo:

```Output
SandBoxHost.cpp
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        fatal error C1001: An internal error has occurred in the compiler.
(compiler file 'msc1.cpp', line 1369)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        note: This diagnostic occurred in the compiler generated function
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted
        to send an error report to Microsoft later.
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

#### <a name="backend-code-generation-crash"></a>Bloqueo de back-end (generación de código)

Los bloqueos de back-end se producen durante la fase de generación de código del compilador. Normalmente, el compilador emitirá el mensaje [Error irrecuperable C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) y podría no hacer referencia al archivo de código fuente y al número de línea asociados al problema. A menudo mencionará el archivo compiler\\utc\\src\\p2\\main.c, pero puede pasar por alto este detalle.

Para este tipo de bloqueo, proporcione una [reproducción de vínculo](#link-repros) si usa la Generación de código en tiempo de vínculo (LTCG), habilitada por el argumento de la línea de comandos **/GL** en cl.exe. De lo contrario, proporcione una [reproducción preprocesada](#preprocessed-repros).

A continuación se muestra un ejemplo de salida del compilador para un bloqueo de back-end en el que no se usa LTCG. Si la salida del compilador tiene este aspecto, debe proporcionar una [reproducción preprocesada](#preprocessed-repros).

```Output
repro.cpp
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:
        An internal error has occurred in the compiler.
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
INTERNAL COMPILER ERROR in
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

Si la línea que empieza por **ERROR INTERNO DEL COMPILADOR** menciona link.exe en lugar de cl.exe, ya se ha habilitado LTCG y debe proporcionar una [reproducción de vínculo](#link-repros). Si en el mensaje de error del compilador no queda claro si se ha habilitado LTCG, puede que tenga que examinar los argumentos de la línea de comandos que copió del registro de compilación en el paso anterior para el argumento de la línea de comandos **/GL**.

#### <a name="linker-crash"></a>Bloqueo del enlazador

Los bloqueos del enlazador se producen durante la fase de vinculación, después de que se haya ejecutado el compilador. Normalmente, el enlazador emitirá el mensaje [Linker Tools Error LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md) (Error de las herramientas del enlazador LNK1000).

> [!NOTE]
> Si la salida menciona C1001 o implica la Generación de código en tiempo de vínculo, vea [Bloqueo de back-end (generación de código)](#backend-code-generation-crash) para obtener más información.

Para este tipo de bloqueo, proporcione una [reproducción de vínculo](#link-repros).

A continuación se muestra un ejemplo de la salida del compilador para este tipo de bloqueo.

```Output
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2

  Version 14.00.22816.0

  ExceptionCode            = C0000005
  ExceptionFlags           = 00000000
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)
        "z:\tools\bin\x64\link.exe"
  NumberParameters         = 00000002
  ExceptionInformation[ 0] = 0000000000000000
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF

CONTEXT:

  Rax    = 0000000000000400  R8     = 0000000000000000
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690
  Rdx    = 000000655F97E270  R11    = 0000000000000400
  Rsp    = 000000655F97E248  R12    = 0000000000000000
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000
  Rsi    = 000000655DF82580  R14    = 000000655F97F390
  Rdi    = 0000000000000000  R15    = 0000000000000000
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206
  SegCs  = 0000000000000033  SegDs  = 000000000000002B
  SegSs  = 000000000000002B  SegEs  = 000000000000002B
  SegFs  = 0000000000000053  SegGs  = 000000000000002B
  Dr0    = 0000000000000000  Dr3    = 0000000000000000
  Dr1    = 0000000000000000  Dr6    = 0000000000000000
  Dr2    = 0000000000000000  Dr7    = 0000000000000000
```

Si la vinculación incremental está habilitada y el bloqueo se ha producido únicamente tras un vínculo inicial correcto (es decir, después de la primera vinculación completa en la que se basa la vinculación incremental posterior), proporcione también una copia de los archivos objeto (.obj) y de biblioteca (.lib) que correspondan a los archivos de código fuente modificados tras completar el vínculo inicial.

#### <a name="bad-code-generation"></a>Generación de código no válido

La generación de código no válido es poco frecuente, pero se produce cuando el compilador genera equivocadamente código incorrecto que hará que la aplicación se bloquee en tiempo de ejecución en lugar de detectar este problema en tiempo de compilación. Si cree que el problema que está experimentando provoca la generación de código no válido, considere el informe como si se tratara de un [bloqueo de back-end (generación de código)](#backend-code-generation-crash).

Para este tipo de bloqueo, proporcione una [reproducción de vínculo](#link-repros) si usa la Generación de código en tiempo de vínculo (LTCG), habilitada por el argumento de la línea de comandos **/GL** en cl.exe. De lo contrario, proporcione una [reproducción preprocesada](#preprocessed-repros).

## <a name="how-to-generate-a-repro"></a>Cómo generar una reproducción

Para que podamos rastrear el origen del problema, es muy importante que proporcione una [reproducción adecuada](#what-makes-a-good-repro). Antes de seguir los pasos que se indican a continuación para tipos de reproducción específicos, intente condensar al máximo el código que muestra el problema. Si es posible, intente eliminar o minimizar las dependencias, los encabezados necesarios y las bibliotecas, además de limitar las opciones del compilador y las definiciones del preprocesador usadas.

A continuación se muestran instrucciones para generar los distintos tipos de reproducciones que se usan para notificar los diversos problemas.

### <a name="preprocessed-repros"></a>Reproducciones preprocesadas

Una *reproducción preprocesada* es un archivo de código fuente único que muestra un problema y que se ha generado a partir de la salida del preprocesador de C utilizando la opción del compilador **/P** en el archivo de código fuente original de la reproducción. Este proceso inserta los encabezados incluidos para quitar las dependencias de archivos de encabezado y archivos de código fuente adicionales, y también resuelve las macros, #ifdefs y otros comandos de preprocesador que podrían depender del entorno local.

> [!NOTE]
> Las reproducciones preprocesadas son menos útiles para los problemas que podrían ser consecuencia de errores de la implementación de biblioteca estándar, porque a menudo se sustituye la implementación más reciente en curso para ver si se ha corregido el problema. En este caso, no preprocese la reproducción y, si no puede reducir el problema a un solo archivo de código fuente, empaquete el código en un archivo .zip o similar, o bien considere la posibilidad de usar una reproducción de proyecto IDE. Para obtener más información, vea [Otras reproducciones](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Para preprocesar un archivo de código fuente

1. Capture los argumentos de línea de comandos usados para generar su reproducción, tal como se indica en la sección [Para informar sobre el contenido de la línea de comandos](#to-report-the-contents-of-the-command-line).

1. Abra el **símbolo del sistema para desarrolladores** que coincida con la arquitectura de configuración y la versión de Visual Studio utilizadas para compilar su proyecto.

1. Cámbielo al directorio que contenga el proyecto de reproducción.

1. En la ventana de la consola del símbolo del sistema para desarrolladores, especifique el comando **cl /P** *arguments* *filename.cpp*, en el que *arguments* representa la lista de argumentos capturados más arriba, y *filename.cpp* es el nombre del archivo de código fuente de la reproducción. Este comando replica la línea de comandos usada para la reproducción, pero detiene la compilación después del paso del prerocesador, y genera la salida del código fuente preprocesado en *filename*.i.

Si preprocesa un archivo de código fuente de C++/CX o usa la característica de módulos de C++, se requieren algunos pasos adicionales. Para más información, vea la sección siguiente.

Cuando haya generado el archivo preprocesado, es recomendable que se asegure de que el problema todavía se pueda seguir reproduciendo con el archivo preprocesado.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Para confirmar que el error todavía se reproduce con el archivo preprocesado

1. En la ventana de la consola del símbolo del sistema para desarrolladores, especifique el comando **cl** *arguments* **/TP** *filename*.i para indicar a cl.exe que compile el archivo preprocesado como archivo de código fuente de C++, en el que *arguments* representa la lista de argumentos capturados antes, pero sin los argumentos **/D** y **/I** (porque ya se han incluido en el archivo preprocesado), y en el que *filename*.i es el nombre del archivo preprocesado.

1. Confirme que el problema se reproduce.

Por último, adjunte a su informe la reproducción preprocesada *filename*.i.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Reproducciones de código de C++/CX preprocesadas para WinRT/UWP

Si usa C++/CX para compilar el archivo ejecutable, se requieren algunos pasos adicionales para crear y validar una reproducción preprocesada.

#### <a name="to-preprocess-ccx-source-code"></a>Para preprocesar el código fuente de C++/CX

1. Cree un archivo de código fuente preprocesado tal y como se describe en [Para preprocesar un archivo de código fuente](#to-preprocess-a-source-code-file).

1. Busque el archivo _nombre de archivo_.i file generado para directivas de **#using**.

1. Cree una lista de todos los archivos a los que se hace referencia. No incluya los archivos \*.winmd, los archivos platform.winmd y mscorlib.dll de Windows.

Para prepararse para validar que el archivo preprocesado todavía reproduce el problema.

1. Cree un directorio para el archivo preprocesado y copie el archivo en el nuevo directorio.

1. Copie los archivos .winmd de la lista **#using** en el nuevo directorio.

1. Cree un archivo vccorlib.h vacío en el nuevo directorio.

1. Modifique el archivo preprocesado para quitar las directivas **#using** de mscorlib.dll.

1. Modifique el archivo preprocesado para dejar las rutas de acceso absolutas en solo los nombres de archivo para los archivos .winmd copiados.

Confirme que el archivo preprocesado todavía reproduce el problema tal y como se indica anteriormente.

### <a name="preprocessed-c-modules-repros"></a>Reproducciones de módulos de C++ preprocesados

Si utiliza la característica de módulos del compilador de C++, se requieren algunos pasos distintos para crear y validar una reproducción preprocesada.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Para preprocesar un archivo de código fuente que usa un módulo

1. Capture los argumentos de línea de comandos usados para generar su reproducción, tal como se indica en la sección [Para informar sobre el contenido de la línea de comandos](#to-report-the-contents-of-the-command-line).

1. Abra el **símbolo del sistema para desarrolladores** que coincida con la arquitectura de configuración y la versión de Visual Studio utilizadas para compilar su proyecto.

1. Cámbielo al directorio que contenga el proyecto de reproducción.

1. En la ventana de la consola del símbolo del sistema para desarrolladores, especifique el comando **cl /P** *arguments* *filename.cpp*, en el que *arguments* representa la lista de argumentos capturados anteriormente y *filename.cpp* es el nombre del archivo de código fuente que utiliza el módulo.

1. Cambie al directorio que contiene el proyecto de reproducción que compila la interfaz del módulo (la salida de .ifc).

1. Capture los argumentos de línea de comandos que se utilizan para compilar la interfaz de módulo.

1. En la ventana de la consola del símbolo del sistema para desarrolladores, especifique el comando **cl /P** *arguments* *modulename.ixx*, en el que *arguments* representa la lista de argumentos capturados anteriormente y *modulename.ixx* es el nombre del archivo de que crea la interfaz del módulo.

Cuando haya generado el archivo preprocesado, conviene que compruebe que el problema todavía puede seguir reproduciéndose con el archivo preprocesado.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Para confirmar que el error todavía se reproduce con el archivo preprocesado

1. En la ventana de la consola del símbolo del sistema para desarrolladores, vuelva al directorio que contiene el proyecto de reproducción.

1. Escriba el comando **cl** *arguments* **/TP** *filename*i., tal y como se indica anteriormente, para compilar el archivo preprocesado como si fuera un archivo de código fuente de C++.

1. Confirme que el archivo preprocesado todavía reproduce el problema.

Por último, adjunte los archivos de reproducción preprocesados (*filename*i. y *modulename*i.) con la salida de .ifc al informe.

### <a name="link-repros"></a>Reproducciones de vínculo

Una *reproducción de vínculo* es el contenido generado por el vinculador de un directorio especificado por la variable de entorno **link\_repro**. Contiene los artefactos de compilación que muestran conjuntamente un problema que se produce durante el tiempo de vínculo, como un bloqueo de back-end que implica la Generación de código en tiempo de vínculo (LTCG) o bien un bloqueo del vinculador. Estos artefactos de compilación son los que se necesitan como entrada de vinculador para que el problema pueda reproducirse. Las reproducciones de vínculo pueden crearse fácilmente usando esta variable de entorno para habilitar la capacidad de generación de reproducciones integrada del vinculador.

#### <a name="to-generate-a-link-repro"></a>Para generar una reproducción de vínculo

1. Capture los argumentos de línea de comandos usados para generar su reproducción, tal como se indica en la sección [Para informar sobre el contenido de la línea de comandos](#to-report-the-contents-of-the-command-line).

1. Abra el **símbolo del sistema para desarrolladores** que coincida con la arquitectura de configuración y la versión de Visual Studio utilizadas para compilar su proyecto.

1. En la ventana de la consola del símbolo del sistema para desarrolladores, cámbielo al directorio que contenga su proyecto de reproducción.

1. Escriba **mkdir linkrepro** para crear un directorio para la reproducción de vínculo.

1. Escriba el comando **set link\_repro=linkrepro** para establecer la variable de entorno **link\_repro** en el directorio que acaba de crear. Si la compilación se ejecuta desde un directorio diferente, como suele ser el caso de los proyectos más complejos, es mejor establecer **link\_repro** en la ruta de acceso completa al directorio linkrepro.

1. Para generar el proyecto de reproducción en Visual Studio, escriba el comando **devenv** en la ventana de la consola del símbolo del sistema para desarrolladores. De este modo se garantiza que el valor de la variable de entorno **link\_repro** sea visible en Visual Studio. Para compilar el proyecto en la línea de comandos, utilice los argumentos de línea de comandos capturados más arriba para duplicar la compilación de reproducción.

1. Compile el proyecto de reproducción y confirme que el problema esperado se haya producido.

1. Si ha usado Visual Studio para generar la compilación, ciérrelo.

1. En la ventana de la consola del símbolo del sistema para desarrolladores, escriba el comando **set link\_repro=** para borrar la variable de entorno **link\_repro**.

Por último, comprima todo el directorio de la reproducción de vínculo en un archivo .zip o similar para empaquetar la reproducción y adjúntelo al informe.

### <a name="other-repros"></a>Otras reproducciones

Si no es posible reducir el problema a un solo archivo de código fuente o reproducción preprocesada y el problema no requiere una reproducción de vínculo, podemos investigar un proyecto IDE. Se siguen aplicando todas las instrucciones sobre cómo crear una buena reproducción. Por lo tanto, el código debe ser mínimo y autocontenido, el problema debe producirse en las herramientas más recientes y, si procede, el problema no debe verse en otros compiladores.

Cree la reproducción como un proyecto IDE mínimo, comprima toda la estructura de directorios en un archivo .zip o similar para empaquetarlo y adjúntelo al informe.

## <a name="ways-to-send-your-report"></a>Maneras de enviar el informe

Puede enviarnos el informe de dos maneras. Puede usar la [herramienta integrada Notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) de Visual Studio o las páginas de la [comunidad de desarrolladores de Visual Studio](https://developercommunity.visualstudio.com/). También puede ir directamente a las páginas de nuestra comunidad de desarrolladores; para ello, seleccione el botón **Product feedback** (Comentario sobre el producto) situado en la parte inferior de esta página. La elección depende de si quiere utilizar las herramientas integradas en el IDE para realizar capturas de pantalla y organizar el informe para su publicación en las páginas de la comunidad de desarrolladores o si prefiere usar el sitio web directamente.

> [!NOTE]
> Independientemente de cómo envíe el informe, Microsoft respeta su privacidad. Microsoft se compromete a cumplir todas las leyes y los reglamentos sobre privacidad de datos. Para obtener información sobre cómo tratamos los datos que nos envía, vea la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

### <a name="use-the-report-a-problem-tool"></a>Usar la herramienta Notificar un problema

La herramienta **Notificar un problema** de Visual Studio permite a los usuarios de Visual Studio informar sobre diversos problemas en pocos clics. Proporciona un formulario sencillo que puede usar para especificar información detallada sobre el problema que ha encontrado y enviar el informe sin tener que salir del IDE.

Informar de un problema a través de la herramienta **Notificar un problema** del entorno de desarrollo integrado es fácil y útil. Para acceder a ella, elija el icono **Enviar comentarios** que encontrará junto al cuadro de búsqueda **Inicio rápido** de la barra de título. También la encontrará en la barra de menú, en **Ayuda** > **Enviar comentarios** > **Notificar un problema**.

Si elige informar de un error, primero intente encontrar problemas similares en la comunidad de desarrolladores. Si hay alguien que ya ha informado del problema en cuestión, vote a favor del tema y agregue sus comentarios con más detalles al respecto. Si no encuentra ningún problema similar, haga clic en **Informar de un problema nuevo**, en la parte inferior del cuadro de diálogo de Comentarios de Visual Studio, y siga los pasos para notificar el problema.

### <a name="use-the-visual-studio-developer-community-pages"></a>Uso de las páginas de la comunidad de desarrolladores de Visual Studio

Las páginas de la comunidad de desarrolladores de Visual Studio son otra forma muy útil de notificar problemas y encontrar soluciones para Visual Studio, el compilador de C++, las herramientas y las bibliotecas. Hay páginas específicas de la comunidad de desarrolladores de [Visual Studio](https://developercommunity.visualstudio.com/spaces/8/index.html), [Visual Studio para Mac](https://developercommunity.visualstudio.com/spaces/41/index.html), [.NET](https://developercommunity.visualstudio.com/spaces/61/index.html), [C++](https://developercommunity.visualstudio.com/spaces/62/index.html), [ Azure DevOps](https://developercommunity.visualstudio.com/spaces/21/index.html) y [TFS](https://developercommunity.visualstudio.com/spaces/22/index.html). Debajo de estas pestañas, cerca de la parte superior de cada página, verá un cuadro de búsqueda que puede utilizar para encontrar publicaciones o temas en los que se informa de problemas similares. Es posible que ya esté disponible una solución u otra información útil relacionada con su problema. Si alguien ya ha notificado el mismo problema, vote a favor del tema y escriba su comentario en él, en lugar de crear otro tema sobre lo mismo. Para comentar, votar o notificar un problema nuevo, es posible que se le solicite que inicie sesión en su cuenta de Visual Studio y acepte ofrecer acceso a su perfil a la aplicación de la comunidad de desarrolladores.

En el caso de problemas relacionados con el compilador de C++, el enlazador y otras herramientas y bibliotecas, use la página de [C++](https://developercommunity.visualstudio.com/spaces/62/index.html). Si busca el problema y todavía nadie ha informado sobre él, haga clic en el botón **Notificar un problema** que encontrará junto al cuadro de búsqueda de la parte superior de la página. Puede incluir el código y la línea de comandos para reproducir el problema, capturas de pantalla, vínculos a debates relacionados y cualquier otra información que crea útil y oportuna.

> [!TIP]
> Para otros tipos de problemas que pueden surgir en Visual Studio que no están relacionadas con el conjunto de herramientas de C++ (por ejemplo, problemas de la interfaz de usuario, una funcionalidad del IDE interrumpida o bloqueos generales), use la herramienta **Notificar un problema** en el IDE. Esta es la mejor opción, debido a sus funcionalidades de captura de pantalla y su capacidad de grabar las acciones de la interfaz de usuario que conducen al problema que se ha encontrado. Estos tipos de errores también se pueden buscar en el sitio de la [comunidad de desarrolladores](https://developercommunity.visualstudio.com/). Para más información, vea [Cómo notificar un problema con Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017).

### <a name="reports-and-privacy"></a>Informes y privacidad

De forma predeterminada, **toda la información de los informes, así como los comentarios y las respuestas están visibles públicamente**. Normalmente, esto es una ventaja, porque permite que toda la comunidad ver los problemas, las soluciones y las soluciones alternativas que han encontrado otros usuarios. Aunque si le preocupa que por motivos de propiedad intelectual o privacidad se publiquen sus datos o su identidad, tiene otras opciones.

Si le preocupa que se revele su identidad, [cree una cuenta de Microsoft](https://signup.live.com/) que no divulgue ningún detalle sobre usted. Utilice esta cuenta para crear el informe.

**No incluya nada que no quiera revelar en el título ni el contenido del informe inicial, que es público.** En cambio, tenga en cuenta que enviará detalles de forma privada en un comentario aparte. Para asegurarse de que el informe se dirige a las personas adecuadas, incluya **cppcompiler** en la lista de temas del informe de problemas. Ahora es posible especificar quién puede ver las respuestas y los datos adjuntos una vez creado el informe de problemas.

#### <a name="to-create-a-problem-report-for-private-information"></a>Para crear un informe de problemas con información privada

1. En el informe que ha creado, elija **Agregar comentario** para crear la descripción privada del problema.

1. En el editor respuestas, use el control de lista desplegable que aparece debajo de los botones **Enviar** y **Cancelar** para especificar los destinatarios de la respuesta. Solo las personas que especifique podrán ver estas respuestas privadas y las imágenes, los vínculos o el código que incluya en ellos. Elija **Viewable by moderators and the original poster** (Visible para los moderadores y el autor de la publicación original) para limitar la visibilidad a los empleados de Microsoft y a usted mismo.

1. Agregue la descripción y cualquier otra información, imágenes y datos adjuntos de archivo necesarios para la reproducción. Elija el botón **Enviar** para enviar esta información de forma privada.

   Tenga en cuenta que hay un límite de 2 GB en archivos adjuntos y un máximo de 10 archivos. Para una carga mayor, solicite una dirección URL de carga en el comentario privado.

Todas las respuestas incluidas en este comentario tienen la misma visibilidad restringida que haya especificado. Esto se cumple aunque el control de lista desplegable de respuestas no muestre el estado de visibilidad restringida correctamente.

Para preservar su privacidad y mantener la información confidencial fuera de la vista pública, tenga cuidado de mantener todas las interacciones con Microsoft sobre respuestas en este comentario restringido. Las respuestas a otros comentarios pueden provocar que accidentalmente se divulgue información confidencial.

## <a name="how-to-report-a-c-documentation-issue"></a>Cómo informar de un problema con la documentación de C++

Los problemas de GitHub nos sirven para llevar un seguimiento de los problemas que se van detectando en la documentación. Ahora, puede crear problemas de GitHub directamente desde una página de contenido, lo que le permitirá interactuar de forma mucho más satisfactoria con los redactores y los equipos de producto. Si ve un problema en un documento, un ejemplo de código incorrecto, una explicación confusa, que falta algo fundamental o, simplemente, un error tipográfico, nos lo puede hacer saber con total facilidad. Vaya al final de la página y seleccione **Sign in to give documentation feedback** (Iniciar sesión para enviar comentario sobre la documentación). Deberá crear una cuenta de GitHub (si aún no tiene una), pero en cuanto lo haga, podrá ver todos los problemas relativos a la documentación y su estado, así como recibir notificaciones cuando se realicen cambios en relación con el problema que le ocupa. Para más información, vea [A New Feedback System Is Coming to docs.microsoft.com](/teamblog/a-new-feedback-system-is-coming-to-docs) (Un nuevo sistema de comentarios llega a docs.microsoft.com).

Cuando cree un problema de documentación en GitHub con el botón de comentario sobre documentación, el problema se rellena automáticamente con información de la página sobre la que esté creando el problema. Así sabremos cómo localizarlo. No modifique esta información; simplemente, incluya detalles sobre lo que no está bien y, si quiere, háganos una sugerencia sobre cómo corregirlo. [La documentación es de código abierto](https://github.com/MicrosoftDocs/cpp-docs/), por lo que si quiere realizar la corrección y proponerla usted mismo, puede hacerlo. Para más información sobre cómo puede contribuir en la documentación, vea nuestra [guía de contribución](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) en GitHub.

