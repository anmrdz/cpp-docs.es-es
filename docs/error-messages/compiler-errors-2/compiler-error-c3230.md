---
title: Error del compilador C3230 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3230
dev_langs:
- C++
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f74e17b1dec3aba78a38d993da81995d00c93784
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065609"
---
# <a name="compiler-error-c3230"></a>Error del compilador C3230

'función': el argumento de tipo de plantilla para 'plantilla' no puede contener un parámetro de tipo genérico: 'parámetro'

Las instancias de las plantillas se crean en tiempo de compilación, mientras que las instancias de los genéricos se crean en tiempo de ejecución. Por consiguiente, no es posible generar código genérico que pueda llamar a la plantilla, porque no se pueden crear instancias de la plantilla en tiempo de ejecución si finalmente se conoce el tipo genérico.

El ejemplo siguiente genera la advertencia C3230:

```
// C3230.cpp
// compile with: /clr /LD
template <class S>
void f(S t);

generic <class U>
ref class C {
   void f1(U x) {
      f(x);   // C3230
   }
};
```