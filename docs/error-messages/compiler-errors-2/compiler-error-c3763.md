---
title: Error del compilador C3763 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3763
dev_langs:
- C++
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db0304cf0dca69c101ee3e559052ca139caa8be3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030278"
---
# <a name="compiler-error-c3763"></a>Error del compilador C3763

'type': 'retval' y 'out' solo puede aparecer en un tipo de puntero de datos

El [out](../../windows/out-cpp.md) o [retval](../../windows/retval.md) atributos solo pueden aparecer en los parámetros de tipo puntero. Quite el atributo o haga que el parámetro de tipo puntero.

El ejemplo siguiente genera C3763:

```
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```