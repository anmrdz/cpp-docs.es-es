---
title: Error del compilador C3824 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03d42f80716b81f4409449262af650220b1ad92b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083956"
---
# <a name="compiler-error-c3824"></a>Error del compilador C3824

'member': este tipo no puede aparecer en este contexto (parámetro de función, tipo de valor devuelto o un miembro estático)

Punteros anclados no pueden ser parámetros de función, tipos de valor devuelto o declara `static`.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3824:

```
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
