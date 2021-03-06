---
title: bool auto_gcroot::operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_gcroot.operator bool
- auto_gcroot::operator bool
- msclr.auto_gcroot.operator bool
- msclr::auto_gcroot::operator bool
- operator bool
dev_langs:
- C++
helpviewer_keywords:
- bool operator
ms.assetid: 87d38498-4221-4de8-8d02-c2dd2e6274ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c2fe517809db7cecacc7a0190e0dae94ef55c35d
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161195"
---
# <a name="autogcrootoperator-bool"></a>auto_gcroot::operator bool

Operador para el uso de `auto_gcroot` en una expresión condicional.

## <a name="syntax"></a>Sintaxis

```
operator bool() const;
```

## <a name="return-value"></a>Valor devuelto

**True** si el objeto ajustado es válido; **false** en caso contrario.

## <a name="remarks"></a>Comentarios

Este operador convierte realmente en `_detail_class::_safe_bool` que es más seguro que **bool** porque no se puede convertir a un tipo entero.

## <a name="example"></a>Ejemplo

```cpp
// msl_auto_gcroot_operator_bool.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s;
   if ( s ) Console::WriteLine( "s is valid" );
   if ( !s ) Console::WriteLine( "s is invalid" );
   s = "something";
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
   s.reset();
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
}
```

```Output
s is invalid
now s is valid
now s is invalid
```

## <a name="requirements"></a>Requisitos

**Archivo de encabezado** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>Vea también

[auto_gcroot (Miembros)](../dotnet/auto-gcroot-members.md)<br/>
[auto_gcroot::operator!](../dotnet/auto-gcroot-operator-logical-not.md)