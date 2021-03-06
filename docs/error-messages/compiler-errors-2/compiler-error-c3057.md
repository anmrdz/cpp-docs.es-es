---
title: Error del compilador C3057 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3057
dev_langs:
- C++
helpviewer_keywords:
- C3057
ms.assetid: b0b2ba88-9c74-4bec-bf60-8fc72eade34c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b01c195ff05631f4bbf9d9d426f91dd94282d4bb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058826"
---
# <a name="compiler-error-c3057"></a>Error del compilador C3057

'símbolo': la inicialización dinámica de los símbolos 'threadprivate' no se admite actualmente.

El valor inicializado de un símbolo usado en una cláusula [threadprivate](../../parallel/openmp/reference/threadprivate.md) debe conocerse en tiempo de compilación.

El ejemplo siguiente genera la advertencia C3057:

```
// C3057.cpp
// compile with: /openmp /c
extern int f();
int x, y = f();
int a, b;
#pragma omp threadprivate(x, y)   // C3057

#pragma omp threadprivate(a, b)

int main() {
   // Delete the following 4 lines to resolve.
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }

   #pragma omp parallel copyin(a, b)
   {
      a = b;
   }
}
```

El ejemplo siguiente genera la advertencia C3057:

```
// C3057b.cpp
// compile with: /openmp /c
extern int Initialize();
int main() {
   #pragma omp parallel
   {
      static int var = Initialize();
      #pragma omp threadprivate(var)   // C3057
   }

   // OK
   #pragma omp parallel
   {
      static int var2;
      static bool initialized2;
      #pragma omp threadprivate(var2, initialized2)
      if (!initialized2) {
         var2 = Initialize();
         initialized2 = true;
      }
   }
}
```