---
title: system (Función) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edb78056e5152485677a14a934c5dcbbc464d862
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098439"
---
# <a name="system-function"></a>system (Función)

**ANSI 4.10.4.5** Contenido y modo de ejecución de la cadena por la función **system**

La función **system** ejecuta un comando interno del sistema operativo, o un archivo .EXE, .COM (.CMD en Windows NT) o .BAT dentro de un programa de C, en lugar de la línea de comandos.

La función system encuentra el intérprete de comandos, que es normalmente CMD.EXE en el sistema operativo Windows NT o COMMAND.COM en Windows. Después, la función system pasa la cadena del argumento al intérprete de comandos.

Para más información, vea [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).

## <a name="see-also"></a>Vea también

[Funciones de la biblioteca](../c-language/library-functions.md)