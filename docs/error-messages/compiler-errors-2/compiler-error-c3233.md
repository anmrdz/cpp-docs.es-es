---
title: Error del compilador C3233 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3233
dev_langs:
- C++
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87a5494e4894077d6f9dc61d920ed42db9872988
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035453"
---
# <a name="compiler-error-c3233"></a>Error del compilador C3233

'type': parámetro de tipo genérico ya restringido

No se puede restringir un parámetro genérico en más de una cláusula `where` .

El ejemplo siguiente genera la advertencia C3233.

```
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```