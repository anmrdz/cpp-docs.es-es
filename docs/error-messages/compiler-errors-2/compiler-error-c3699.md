---
title: Error del compilador C3699 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3699
dev_langs:
- C++
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64e5a5bb98f9e8a6950bbb279c026f167a2ee92e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107722"
---
# <a name="compiler-error-c3699"></a>Error del compilador C3699

'operador': no se puede utilizar este direccionamiento indirecto en el tipo 'type'

Se intentó usar el direccionamiento indirecto no permitido en `type`.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3699.

```
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>Ejemplo

Una propiedad trivial no puede tener tipo de referencia. Vea [property](../../windows/property-cpp-component-extensions.md) para obtener más información. El ejemplo siguiente genera C3699.

```
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>Ejemplo

El equivalente de una sintaxis de "puntero a un puntero" es un identificador para una referencia de seguimiento. El ejemplo siguiente genera C3699.

```
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```