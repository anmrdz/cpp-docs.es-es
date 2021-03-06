---
title: Error del compilador de recursos RW2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2001
dev_langs:
- C++
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f401ce7c9a96cfeecf195b8872a704b8b1291939
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114987"
---
# <a name="resource-compiler-error-rw2001"></a>Error del compilador de recursos RW2001

Directiva no válida en el archivo RC preprocesado

El archivo RC contiene un **#pragma** directiva.

Use la **#ifndef** directiva de preprocesador con el **RC_INVOKED** constante que define el compilador de recursos cuando se procesa un archivo de inclusión. Lugar el **#pragma** directiva dentro de un bloque de código que no se procesan cuando el **RC_INVOKED** se define la constante. Código del bloque se procesa solo por el compilador de C/C ++ y no por el compilador de recursos. Ejemplo de código siguiente muestra esta técnica:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

El **#pragma** directiva de preprocesador no tiene ningún significado una. Archivo RC. El **#include** directiva de preprocesador se usa con frecuencia en una. Archivo RC para incluir un archivo de encabezado (un archivo de encabezado personalizado basado en el proyecto o un archivo de encabezado estándar proporcionado por Microsoft con uno de sus productos). Algunos de estos archivos de inclusión contienen la **#pragma** directiva. Dado que un archivo de encabezado puede incluir uno o varios archivos de encabezado, el archivo que contiene la provoca el error **#pragma** directiva puede no ser evidente de inmediato.

El **#ifndef RC_INVOKED** técnica puede controlar los archivos de encabezado en archivos de encabezado basados en proyectos de inclusión.