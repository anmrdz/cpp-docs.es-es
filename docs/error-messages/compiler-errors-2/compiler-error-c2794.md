---
title: Error del compilador C2794 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2794
dev_langs:
- C++
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c81e8dcfde2a24c4a827406c3e499c12e891b2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068018"
---
# <a name="compiler-error-c2794"></a>Error del compilador C2794

'function': no es un miembro de ninguna clase base directa o indirecta de 'class'

Intentó utilizar [super](../../cpp/super.md) para llamar a una función miembro que no existe.

El ejemplo siguiente genera C2794

```
// C2794.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::f();  // C2794
   }
};
```