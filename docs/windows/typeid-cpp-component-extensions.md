---
title: typeid (C++ / c++ / CLI y c++ / CX) | Documentos de Microsoft
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1196956208d490674d4705a8d1e61ea3381d94a2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065192"
---
# <a name="typeid--ccli-and-ccx"></a>typeid (C++ / c++ / CLI y c++ / CX)

Obtiene un valor que indica el tipo de un objeto.

> [!NOTE]
> Este tema hace referencia a la versión de extensiones de componentes de C++ de typeid. Para la versión de ISO C++ de esta palabra clave, consulte [typeid (operador)](../cpp/typeid-operator.md).

## <a name="all-runtimes"></a>Todos los runtimes

### <a name="syntax"></a>Sintaxis

```cpp
T::typeid
```

### <a name="parameters"></a>Parámetros

*T*<br/>
Nombre de tipo.

## <a name="windows-runtime"></a>Windows en tiempo de ejecución

### <a name="syntax"></a>Sintaxis

```cpp
Platform::Type^ type = T::typeid;
```

### <a name="parameters"></a>Parámetros

*T*<br/>
Nombre de tipo.

### <a name="remarks"></a>Comentarios

En C / c++ / CX, typeid devuelve un [Platform:: Type](../cppcx/platform-type-class.md) que se construye a partir de información de tipo en tiempo de ejecución.

### <a name="requirements"></a>Requisitos

Opción del compilador: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="syntax"></a>Sintaxis

```
type::typeid
```

### <a name="parameters"></a>Parámetros

*type*<br/>
El nombre de un tipo (declarador abstracto) para el que desea la `System::Type` objeto.

### <a name="remarks"></a>Comentarios

`typeid` se usa para obtener <xref:System.Type> para un tipo en tiempo de compilación.

`typeid` es similar a obtener System::Type para un tipo en tiempo de ejecución mediante <xref:System.Type.GetType%2A> o <xref:System.Object.GetType%2A>. Sin embargo, typeid solo acepta un nombre de tipo como parámetro.  Si desea usar una instancia de un tipo para obtener su System::Type name, use GetType.

`typeid` debe poder evaluar un nombre de tipo (type) en tiempo de compilación, mientras que GetType evalúa el tipo que se va a devolver en tiempo de ejecución.

`typeid` puede tomar un nombre de tipo nativo o alias de en tiempo de ejecución de lenguaje común para el nombre de tipo nativo; consulte [equivalentes de .NET Framework para tipos nativos de C++ (C++ / c++ / CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) para obtener más información.

`typeid` también funciona con los tipos nativos, aunque todavía devuelve System::Type.  Para obtener una estructura type_info, use [typeid (operador)](../cpp/typeid-operator.md).

### <a name="requirements"></a>Requisitos

Opción del compilador: `/clr`

### <a name="examples"></a>Ejemplos

En el ejemplo siguiente se compara la palabra clave typeid con el `GetType()` miembro.

```cpp
// keyword__typeid.cpp
// compile with: /clr
using namespace System;

ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   Type ^ pType = pG->GetType();
   Type ^ pType2 = G::typeid;

   if (pType == pType2)
      Console::WriteLine("typeid and GetType returned the same System::Type");
   Console::WriteLine(G::typeid);

   typedef float* FloatPtr;
   Console::WriteLine(FloatPtr::typeid);
}
```

```Output
typeid and GetType returned the same System::Type
G

System.Single*
```

En el ejemplo siguiente se muestra que se puede usar una variable de tipo System::Type para obtener los atributos de un tipo.  También muestra que para algunos tipos, tendrá que crear una definición de tipos para usar `typeid`.

```cpp
// keyword__typeid_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

typedef int ^ handle_to_int;
typedef int * pointer_to_int;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref class AtClass {
public:
   AtClass(Type ^) {
      Console::WriteLine("in AtClass Type ^ constructor");
   }
};

[attribute(AttributeTargets::All)]
ref class AtClass2 {
public:
   AtClass2() {
      Console::WriteLine("in AtClass2 constructor");
   }
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
ref class B : Attribute {};

int main() {
   Type ^ MyType = B::typeid;

   Console::WriteLine(MyType->IsClass);

   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);
   for (int i = 0 ; i < MyArray->Length ; i++ )
      Console::WriteLine(MyArray[i]);

   if (int::typeid != pointer_to_int::typeid)
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");

   if (int::typeid == handle_to_int::typeid)
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");
}
```

```Output
True

in AtClass2 constructor

in AtClass Type ^ constructor

AtClass2

System.AttributeUsageAttribute

AtClass

int::typeid != pointer_to_int::typeid, as expected

int::typeid == handle_to_int::typeid, as expected
```

## <a name="see-also"></a>Vea también

[Extensiones de componentes de .NET y UWP](../windows/component-extensions-for-runtime-platforms.md)