---
title: Del compilador (nivel 4) de la advertencia C4100 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4100
dev_langs:
- C++
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6ad1b8bab287f4c16b00781e90351bbb204aa91
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099474"
---
# <a name="compiler-warning-level-4-c4100"></a>Advertencia del compilador (nivel 4) C4100

'identifier': parámetro formal sin referencia

No se hace referencia el parámetro formal en el cuerpo de la función. Se omite el parámetro no referenciado.

También puede emitirse C4100 cuando el código llama a un destructor en un parámetro de tipo primitivo no.  Esta es una limitación del compilador de Visual C++.

El ejemplo siguiente genera el error C4100:

```
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```