---
title: Personalizar el procesamiento de línea de comandos de C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 855562b8b6eb5e577914fc6305668ee7305c86e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110684"
---
# <a name="customizing-c-command-line-processing"></a>Personalizar el procesamiento de línea de comandos de C++

## <a name="microsoft-specific"></a>Específicos de Microsoft

Si el programa no acepta argumentos de línea de comandos, puede guardar una pequeña cantidad de espacio suprimiendo el uso de la rutina de biblioteca que realiza el procesamiento de la línea de comandos. Esta rutina se denomina `_setargv` y se describe en [expansión de caracteres comodín](../cpp/wildcard-expansion.md). Para suprimir su uso, defina una rutina que no hace nada en el archivo que contiene el `main` funcionando y asígnele el nombre `_setargv`. La llamada a `_setargv` , a continuación, se satisface mediante la definición de `_setargv`, y la versión de la biblioteca no está cargada.

De forma similar, si nunca tiene acceso a la tabla de entorno a través de la `envp` argumento, puede proporcionar una rutina vacía propia que se usará en lugar de `_setenvp`, la rutina de procesamiento de entorno. Al igual que con el `_setargv` función, `_setenvp` debe declararse como **extern "C"**.

El programa puede realizar llamadas a la `spawn` o `exec` familia de rutinas en la biblioteca de tiempo de ejecución de C. Si es así, no debe suprimir la rutina de procesamiento de entorno, puesto que esta rutina se utiliza para pasar un entorno del proceso primario al proceso secundario.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[main: Inicio de programa](../cpp/main-program-startup.md)