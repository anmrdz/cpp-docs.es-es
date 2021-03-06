---
title: auto_gcroot::auto_gcroot | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::auto_gcroot
- auto_gcroot::auto_gcroot
- auto_gcroot.auto_gcroot
- msclr.auto_gcroot.auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot::auto_gcroot
ms.assetid: 27faa42a-64ea-4d31-836f-073a55145735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 805a61f439e3527c7cc1a6b52fa54e93128f8d2b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383146"
---
# <a name="autogcrootautogcroot"></a>auto_gcroot::auto_gcroot

El `auto_gcroot` constructor.

## <a name="syntax"></a>Sintaxis

```cpp
auto_gcroot(
   _element_type _ptr = nullptr
);
auto_gcroot(
   auto_gcroot<_element_type> & _right
);
template<typename _other_type>
auto_gcroot(
   auto_gcroot<_other_type> & _right
);
```

#### <a name="parameters"></a>Parámetros

*_ptr*<br/>
El objeto que posea.

*a la _derecha*<br/>
Un `auto_gcroot` existente.

## <a name="remarks"></a>Comentarios

Al construir un `auto_gcroot` partir de una máquina `auto_gcroot`, existente `auto_gcroot` libera su objeto antes de transferir la propiedad del objeto para el nuevo `auto_gcroot`.

## <a name="example"></a>Ejemplo

```cpp
// msl_auto_gcroot_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class RefClassA {
protected:
   String^ m_s;
public:
   RefClassA(String^ s) : m_s(s) {
      Console::WriteLine( "in RefClassA constructor: " + m_s );
   }
   ~RefClassA() {
      Console::WriteLine( "in RefClassA destructor: " + m_s );
   }

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class RefClassB : RefClassA {
public:
   RefClassB( String^ s ) : RefClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

class ClassA { //unmanaged class
private:
   auto_gcroot<RefClassA^> m_a;

public:
   ClassA() : m_a( gcnew RefClassA( "unmanaged" ) ) {}
   ~ClassA() {} //no need to delete m_a

   void DoSomething() {
      m_a->PrintHello();
   }
};

int main()
{
   {
      ClassA a;
      a.DoSomething();
   } // a.m_a is automatically destroyed as a goes out of scope

   {
      auto_gcroot<RefClassA^> a(gcnew RefClassA( "first" ) );
      a->PrintHello();
   }

   {
      auto_gcroot<RefClassB^> b(gcnew RefClassB( "second" ) );
      b->PrintHello();
      auto_gcroot<RefClassA^> a(b); //construct from derived type
      a->PrintHello();
      auto_gcroot<RefClassA^> a2(a); //construct from same type
      a2->PrintHello();
   }

   Console::WriteLine("done");
}
```

```Output
in RefClassA constructor: unmanaged
Hello from unmanaged A!
in RefClassA destructor: unmanaged
in RefClassA constructor: first
Hello from first A!
in RefClassA destructor: first
in RefClassA constructor: second
Hello from second B!
Hello from second A!
Hello from second A!
in RefClassA destructor: second
done
```

## <a name="requirements"></a>Requisitos

**Archivo de encabezado** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>Vea también

[auto_gcroot (Miembros)](../dotnet/auto-gcroot-members.md)<br/>
[auto_gcroot::attach](../dotnet/auto-gcroot-attach.md)<br/>
[auto_gcroot::operator=](../dotnet/auto-gcroot-operator-assign.md)<br/>
[auto_gcroot::~auto_gcroot](../dotnet/auto-gcroot-tilde-auto-gcroot.md)