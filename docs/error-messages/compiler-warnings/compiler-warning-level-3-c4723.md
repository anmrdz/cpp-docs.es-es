---
title: Compilador advertencia (nivel 3) C4723 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4723
dev_langs:
- C++
helpviewer_keywords:
- C4723
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca6715e26705632dc3187cb6db7deed8636cd82
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033152"
---
# <a name="compiler-warning-level-3-c4723"></a>Advertencia del compilador (nivel 3) C4723

posible división por 0

El segundo operando en una operación de división que se evalúa como cero en tiempo de compilación, dando resultados no definidos.

Esta advertencia se emite cuando se usa [/Og](../../build/reference/og-global-optimizations.md) o una opción de optimización que implique/Og.

Puede que el compilador ha generado el operando cero.