---
title: Error del compilador C3492 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3492
dev_langs:
- C++
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54b3689a6ee565788e2a469a8321727a9fdd822f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089221"
---
# <a name="compiler-error-c3492"></a>Error del compilador C3492

'var': no se puede capturar un miembro de una unión anónima.

No se puede capturar un miembro de una unión sin nombre.

### <a name="to-correct-this-error"></a>Para corregir este error

- Asigne un nombre a la unión y pase la estructura de unión completa a la lista de captura de la expresión lambda.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera el error C3492 porque se captura en un miembro de una unión anónima:

```
// C3492a.cpp

int main()
{
   union
   {
      char ch;
      int x;
   };

   ch = 'y';
   [&x](char ch) { x = ch; }(ch); // C3492
}
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se resuelve C3492 dando un nombre a la unión y pasando la estructura de unión completa a la lista de captura de la expresión lambda:

```
// C3492b.cpp

int main()
{
   union
   {
      char ch;
      int x;
   } u;

   u.ch = 'y';
   [&u](char ch) { u.x = ch; }(u.ch);
}
```

## <a name="see-also"></a>Vea también

[Expresiones lambda](../../cpp/lambda-expressions-in-cpp.md)