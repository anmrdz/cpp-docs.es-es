---
title: Compilador advertencia (nivel 1) C4677 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6a3f57ba0e3d4c15c83711a86bb8482fa8b0596
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049395"
---
# <a name="compiler-warning-level-1-c4677"></a>Advertencia del compilador (nivel 1) C4677

'function': signatura de miembro no privado contiene un tipo privado de ensamblado 'tipo_privado'

Un tipo que tiene accesibilidad pública fuera del ensamblado usa un tipo que tiene acceso privado fuera del ensamblado. Un componente que se hace referencia al tipo de ensamblado público no podrá usar el miembro de tipo o los miembros que hacen referencia al tipo privado de ensamblado.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C4677.

```
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```