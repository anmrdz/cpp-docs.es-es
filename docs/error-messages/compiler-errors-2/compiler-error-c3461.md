---
title: Error del compilador C3461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3461
dev_langs:
- C++
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8027831810a8f95b8d72ef70e392d9984b5c2f3a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077937"
---
# <a name="compiler-error-c3461"></a>Error del compilador C3461

'type': solamente se puede reenviar un tipo administrado

El reenvío de tipos solo puede realizarse con tipos CLR.  Consulte [clases y Structs](../../windows/classes-and-structs-cpp-component-extensions.md) para obtener más información.

Para obtener más información, consulte [reenvío de tipos (C++ / c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crea un componente.

```
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C3461.

```
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```