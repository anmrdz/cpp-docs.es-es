---
title: Error del compilador C3121 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3121
dev_langs:
- C++
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9f14d46827e946d619801c1e92dabb33440aa7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056071"
---
# <a name="compiler-error-c3121"></a>Error del compilador C3121

no se puede cambiar el GUID para la clase 'nombre_de_clase'

Ha intentado cambiar el identificador de clase con [__declspec (UUID)](../../cpp/uuid-cpp.md).

Por ejemplo, el código siguiente genera C3121:

```
// C3121.cpp
[emitidl];
[module(name="MyLibrary")];

[coclass, uuid="00000000-0000-0000-0000-111111111111"]
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121
{
};
int main()
{
}
```