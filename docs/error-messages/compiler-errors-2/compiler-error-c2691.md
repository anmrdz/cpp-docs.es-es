---
title: Error del compilador C2691 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2691
dev_langs:
- C++
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe048537ca1d504587fe64fdd5f9b5a43af7c6e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100570"
---
# <a name="compiler-error-c2691"></a>Error del compilador C2691

'tipo de datos': tipo administrado o WinRTarray no puede tener este tipo de elemento

El tipo de un elemento de matriz administrada o de WinRT puede ser un tipo de valor o un tipo de referencia.

El siguiente ejemplo genera el error C2691:

```
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
