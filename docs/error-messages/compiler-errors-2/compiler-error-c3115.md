---
title: Error del compilador C3115 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3115
dev_langs:
- C++
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 716566066a58c20378128ee56d9da0aa070b6e9b
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788700"
---
# <a name="compiler-error-c3115"></a>Error del compilador C3115

'attribute': este atributo no se permite en 'construct'

Un atributo se aplicó a una construcción para que no estaba previsto.  Consulte [atributos por uso](../../windows/attributes/attributes-by-usage.md) para obtener más información.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3115.

```
// C3115.cpp
// compile with: /c
#include <unknwn.h>
[module(name="xx")];

[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115
// try the following line instead
// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI {
   HRESULT xx();
};
```