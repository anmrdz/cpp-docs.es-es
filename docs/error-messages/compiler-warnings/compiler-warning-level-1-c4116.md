---
title: Compilador advertencia (nivel 1) C4116 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4116
dev_langs:
- C++
helpviewer_keywords:
- C4116
ms.assetid: 25434ef3-061e-4252-91a5-0fe2a4b2ffb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f91892bd28733761c187705b8f576007862027b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080706"
---
# <a name="compiler-warning-level-1-c4116"></a>Compilador advertencia (nivel 1) C4116

definición de tipo sin nombre en paréntesis

Una estructura, unión o tipo enumerado sin nombre se define en una expresión entre paréntesis. La definición de tipo no tiene sentida.

En una llamada de función de C, la definición tiene ámbito global. En una llamada de función de C++, la definición tiene el mismo ámbito que la función que se llama.