---
title: Error del compilador C2802 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2802
dev_langs:
- C++
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95b4f64aad9cb14151ca6128bedebcd15ece17ed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061260"
---
# <a name="compiler-error-c2802"></a>Error del compilador C2802

miembro estático 'operator operator' no tiene parámetros formales

Un operador declara un `static` función miembro debe tener al menos un parámetro.

El ejemplo siguiente genera C2802:

```
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```