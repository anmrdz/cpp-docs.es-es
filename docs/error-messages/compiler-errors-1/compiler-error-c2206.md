---
title: Error del compilador C2206 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2206
dev_langs:
- C++
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f1599b927e04f2f9196229bf7c8aaf5e49c13f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060062"
---
# <a name="compiler-error-c2206"></a>Error del compilador C2206

'function' : typedef no se puede utilizar para la definición de función

Se usa una `typedef` para definir un tipo de función.

El ejemplo siguiente genera la advertencia C2206:

```
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```