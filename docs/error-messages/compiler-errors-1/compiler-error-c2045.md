---
title: Error del compilador C2045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2045
dev_langs:
- C++
helpviewer_keywords:
- C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c2de96f6f84e32de6b1eeae285a5210f16192ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115929"
---
# <a name="compiler-error-c2045"></a>Error del compilador C2045

'identificador': etiqueta redefinida

La etiqueta aparece delante de varias instrucciones en una misma función.

El ejemplo siguiente genera la advertencia C2045:

```
// C2045.cpp
int main() {
   label: {
   }
   goto label;
   label: {}   // C2045
}
```