---
title: Error del compilador C3482 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9921c25575888ab2db1c092f9325002d1becb921
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053380"
---
# <a name="compiler-error-c3482"></a>Error del compilador C3482

'this' solo se puede usar como captura lambda en una función miembro no estática

No se puede pasar `this` a la lista de captura de una expresión lambda declarada en un método estático o una función global.

### <a name="to-correct-this-error"></a>Para corregir este error

- Convierta la función de inclusión a un método no estático, o

- Quite el puntero `this` de la lista de captura de la expresión lambda.

## <a name="example"></a>Ejemplo

El siguiente ejemplo genera el error C3482:

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>Vea también

[Expresiones lambda](../../cpp/lambda-expressions-in-cpp.md)