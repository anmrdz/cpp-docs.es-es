---
title: auto_handle auto_handle::operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr.auto_handle.operator auto_handle
- operator auto_handle
- msclr::auto_handle::operator auto_handle
- auto_handle.operator auto_handle
- auto_handle::operator auto_handle
dev_langs:
- C++
helpviewer_keywords:
- operator auto_handle
ms.assetid: 2f8b35d1-2783-4d91-b6fb-eae551270fb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5b9ac6d95855ffa7e8887d086447f519cf78866f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393651"
---
# <a name="autohandleoperator-autohandle"></a>auto_handle::operator auto_handle

Operador de conversión de tipos entre `auto_handle` y tipos compatibles.

## <a name="syntax"></a>Sintaxis

```
template<typename _other_type>
operator auto_handle<_other_type>();
```

## <a name="return-value"></a>Valor devuelto

Actual `auto_handle` convertir a `auto_handle<_other_type>`.

## <a name="example"></a>Ejemplo

```
// msl_auto_handle_op_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {}

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class ClassB : ClassA {
public:
   ClassB( String ^ s) : ClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

int main() {
   auto_handle<ClassB> b = gcnew ClassB("first");
   b->PrintHello();
   auto_handle<ClassA> a = (auto_handle<ClassA>)b;
   a->PrintHello();
}
```

```Output
Hello from first B!
Hello from first A!
```

## <a name="requirements"></a>Requisitos

**Archivo de encabezado** \<msclr\auto_handle.h >

**Namespace** msclr

## <a name="see-also"></a>Vea también

[auto_handle (Miembros)](../dotnet/auto-handle-members.md)