---
title: Error del compilador C2094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2094
dev_langs:
- C++
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e3591fef423bc24562a2f2edf18f7f2774cfcc4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073530"
---
# <a name="compiler-error-c2094"></a>Error del compilador C2094

la etiqueta 'identifier' no estaba definida

La etiqueta que utiliza una instrucción [goto](../../cpp/goto-statement-cpp.md) no existe en la función.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C2094:

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

Posible resolución:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```