---
title: Propiedades generales (proyecto de archivos Make de C++ para Linux) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 3dec6853-43f6-412b-9806-9bfad333a204
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 6fb23d2c7275788b05fe4450613770c268ca6c64
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705704"
---
# <a name="makefile-project-properties-linux-c"></a>Propiedades del proyecto de archivos Make (C++ para Linux)

A continuación se muestra una lista parcial de las propiedades disponibles en un proyecto de archivo Make de Linux. Muchas de las propiedades de los proyectos de archivos Make son idénticas a las de la aplicación de consola de C++ de Linux.

## <a name="general"></a>General

Property | Description | Opciones
--- | ---| ---
Directorio de salida | Especifica una ruta de acceso relativa al directorio de archivos de salida; puede incluir variables de entorno.
Directorio intermedio | Especifica una ruta de acceso relativa al directorio de archivos intermedios; puede incluir variables de entorno.
Archivo de registro de compilación | Especifica el archivo de registro de compilación en el que se escribe cuando está habilitada la opción de registro de compilación.
Tipo de configuración | Especifica el tipo de salida que genera esta configuración. | **Biblioteca dinámica (.so)**: biblioteca dinámica (.so)<br>**Biblioteca estática (.a)**: biblioteca estática (.a)<br>**Aplicación (.out)**: aplicación (.out)<br>**Archivo Make**: archivo Make<br>
Máquina de compilación remota | Máquina o dispositivo de destino que debe usarse para la compilación, implementación y depuración remotas.
Directorio raíz de la compilación remota | Especifica una ruta de acceso a un directorio de la máquina o el dispositivo remotos.
Directorio del proyecto de compilación remota | Especifica una ruta de acceso a un directorio de la máquina o el dispositivo remotos para el proyecto.

## <a name="debugging"></a>Depuración

Vea [Propiedades del depurador (C++ para Linux)](debugging-linux.md)

## <a name="copy-sources"></a>Copiar orígenes

Vea [Propiedades del proyecto Copiar orígenes (C++ para Linux)](copy-sources-project.md).

## <a name="build-events"></a>Eventos de compilación

### <a name="pre-build-event"></a>Evento anterior a la compilación

Property | Description
--- | ---
Línea de comandos | Especifica una línea de comandos para ejecutar la herramienta de eventos anteriores a la compilación.
Description | Especifica una descripción que se mostrará para la herramienta de eventos anteriores a la compilación.
Usar en la compilación | Especifica si este evento de compilación se excluirá de la compilación en la configuración actual.
Archivos adicionales para copiar | Especifica archivos adicionales para copiar en el sistema remoto. También se puede proporcionar la lista en forma de pares de asignaciones de local a remoto usando esta sintaxis: rutaDeAccesoLocalCompleta1:=rutaDeAccesoRemotaCompleta1;rutaDeAccesoLocalCompleta2:=rutaDeAccesoRemotaCompleta2, donde un archivo local se puede copiar en la ubicación remota especificada del sistema remoto.

### <a name="post-build-event"></a>Evento posterior a la compilación

Property | Description
--- | ---
Línea de comandos | Especifica una línea de comandos para ejecutar la herramienta de eventos posteriores a la compilación.
Description | Especifica una descripción que se mostrará para la herramienta de eventos posteriores a la compilación.
Usar en la compilación | Especifica si este evento de compilación se excluirá de la compilación en la configuración actual.
Archivos adicionales para copiar | Especifica archivos adicionales para copiar en el sistema remoto. También se puede proporcionar la lista en forma de pares de asignaciones de local a remoto usando esta sintaxis: rutaDeAccesoLocalCompleta1:=rutaDeAccesoRemotaCompleta1;rutaDeAccesoLocalCompleta2:=rutaDeAccesoRemotaCompleta2, donde un archivo local se puede copiar en la ubicación remota especificada del sistema remoto.

### <a name="remote-pre-build-event"></a>Evento remoto anterior a la compilación

Property | Description
--- | ---
Línea de comandos | Especifica una línea de comandos para que la ejecute la herramienta de eventos anteriores a la compilación en el sistema remoto.
Description | Especifica una descripción que se mostrará para la herramienta de eventos anteriores a la compilación.
Usar en la compilación | Especifica si este evento de compilación se excluirá de la compilación en la configuración actual.
Archivos adicionales para copiar | Especifica archivos adicionales que se copiarán del sistema remoto. También se puede proporcionar la lista en forma de pares de asignaciones de remoto a local usando la sintaxis siguiente: rutaDeAccesoRemotaCompleta1:=rutaDeAccesoLocalCompleta1;rutaDeAccesoRemotaCompleta2:=rutaDeAccesoLocalCompleta2, donde un archivo remoto se puede copiar en la ubicación especificada de la máquina local.

### <a name="remote-post-build-event"></a>Evento remoto posterior a la compilación

Property | Description
--- | ---
Línea de comandos | Especifica una línea de comandos para que la ejecute la herramienta de eventos posteriores a la compilación en el sistema remoto.
Description | Especifica una descripción que se mostrará para la herramienta de eventos posteriores a la compilación.
Usar en la compilación | Especifica si este evento de compilación se excluirá de la compilación en la configuración actual.
Archivos adicionales para copiar | Especifica archivos adicionales que se copiarán del sistema remoto. También se puede proporcionar la lista en forma de pares de asignaciones de remoto a local usando la sintaxis siguiente: rutaDeAccesoRemotaCompleta1:=rutaDeAccesoLocalCompleta1;rutaDeAccesoRemotaCompleta2:=rutaDeAccesoLocalCompleta2, donde un archivo remoto se puede copiar en la ubicación especificada de la máquina local.

## <a name="cc"></a>C/C++

### <a name="intellisense"></a>IntelliSense

Las propiedades de IntelliSense se pueden establecer en el nivel de proyecto o de archivo para proporcionar pistas sobre el motor de IntelliSense. No afectan a la compilación.

Property | Description
--- | ---
Ruta de acceso de búsqueda de inclusión | Especifica la ruta de acceso de búsqueda de inclusión para resolver archivos incluidos.
Archivos de inclusión forzados | Especifica los archivos de inclusión forzada.
Definiciones de preprocesador | Especifica las definiciones del preprocesador que usan los archivos de código fuente.
Anular definiciones del preprocesador | Especifica la anulación de una o varias definiciones del preprocesador.     (/U[macro])
Opciones adicionales | Especifica modificadores de compilador adicionales que IntelliSense usará al analizar archivos de C++.

### <a name="build"></a>Compilar

Property | Description
--- | ---
Línea de comandos de Compilar | Especifica la línea de comandos que se ejecuta para el comando "Compilar".
Línea de comandos de Recompilar todo | Especifica la línea de comandos que se ejecuta para el comando "Recompilar todo".
Línea de comandos de limpieza | Especifica la línea de comandos que se ejecuta para el comando "Limpiar".

### <a name="remote-build"></a>Compilación remota

Property | Description
--- | ---
Línea de comandos de Compilar | Especifica la línea de comandos que se ejecuta para el comando "Compilar". Esto se ejecuta en el sistema remoto.
Línea de comandos de Recompilar todo | Especifica la línea de comandos que se ejecuta para el comando "Recompilar todo". Esto se ejecuta en el sistema remoto.
Línea de comandos de limpieza | Especifica la línea de comandos que se ejecuta para el comando "Limpiar". Esto se ejecuta en el sistema remoto.
Salidas | Especifica las salidas generadas por la compilación remota en el sistema remoto.
