---
title: Error irrecuperable C1311 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d93aa28d0cef3c07fd469349d485c4009fa4771d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091067"
---
# <a name="fatal-error-c1311"></a>Error irrecuperable C1311

El formato COFF no puede inicializar estáticamente 'var' con número bytes de una dirección

Una dirección cuyo valor no se conoce en tiempo de compilación no se puede asignar estáticamente a una variable cuyo tipo tiene el almacenamiento de menos de cuatro bytes.

Este error puede producirse en el código que en caso contrario es válido de C++.

El ejemplo siguiente muestra una condición que podría causar C1311.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```