---
title: Error del compilador C3052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3052
dev_langs:
- C++
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d292087aefcc7bb99e505aefd0534dd018b2725
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049226"
---
# <a name="compiler-error-c3052"></a>Error del compilador C3052

'var': la variable no aparece en la cláusula de uso compartido de datos bajo una cláusula default(none)

Si se usa [default(none)](../../parallel/openmp/reference/default-openmp.md) , cualquier variable usada en el bloque estructurado se debe especificar explícitamente como [shared](../../parallel/openmp/reference/shared-openmp.md) o [private](../../parallel/openmp/reference/private-openmp.md).

El ejemplo siguiente genera la advertencia C3052:

```
// C3052.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(none) // shared(n1) private(n1)
   {
      n1 = 0;   // C3052 use either a shared or private clause
   }
}
```