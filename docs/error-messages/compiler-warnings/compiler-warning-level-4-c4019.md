---
title: Compilador advertencia (nivel 4) C4019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4019
dev_langs:
- C++
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48915f72acdaf0b02acd04de38f10fcdb2a20e93
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065333"
---
# <a name="compiler-warning-level-4-c4019"></a>Advertencia del compilador (nivel 4) C4019

instrucción vacía en ámbito global

Un punto y coma en el ámbito global no está precedido por una instrucción.

Esta advertencia se puede corregir si se quita el punto y coma adicional.

## <a name="example"></a>Ejemplo

```
// C4019.c
// compile with: /Za /W4
#define declint( varname ) int varname;
declint( a );   // C4019, int a;;
declint( b )   // OK, int b;

int main()
{
}
```