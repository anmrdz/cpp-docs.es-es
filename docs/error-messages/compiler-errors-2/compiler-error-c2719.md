---
title: Error del compilador C2719 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4423352bad520d66920a01542f592ed8022482d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054192"
---
# <a name="compiler-error-c2719"></a>Error del compilador C2719

'parameter': el parámetro formal con __declspec(align('#')) no se alineará

El [alinear](../../cpp/align-cpp.md) `__declspec` modificador no está permitido en parámetros de función. La alineación de los parámetros de función se controla mediante la convención de llamada que se utiliza. Para obtener más información, consulte [convenciones de llamada](../../cpp/calling-conventions.md).

El siguiente ejemplo genera el error C2719 y muestra cómo corregirlo:

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```