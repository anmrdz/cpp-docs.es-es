---
title: Error del compilador C3215 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3215
dev_langs:
- C++
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea9b7cb22f5a3d61a661d7344673bf567f7d629
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093901"
---
# <a name="compiler-error-c3215"></a>Error del compilador C3215

'type1': el parámetro de tipo genérico ya estaba restringido por 'type2'

Se especificó una restricción más de una vez.

Para más información sobre genéricos, vea [Generics](../../windows/generics-cpp-component-extensions.md).

El ejemplo siguiente genera la advertencia C3215:

```
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

Posible resolución:

```
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```