---
title: Reemplazar (C++ / c++ / CLI y c++ / CX) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d97558dc50adc0bac8758d0821badff14707c04
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056144"
---
# <a name="override--ccli-and-ccx"></a>Reemplazar (C++ / c++ / CLI y c++ / CX)

El **invalidar** palabra clave contextual indica que un miembro de un tipo invalida una clase base o un miembro de interfaz base.

## <a name="remarks"></a>Comentarios

El **invalidar** palabra clave es válida cuando se compila para destinos nativos (opción del compilador predeterminada), los destinos en tiempo de ejecución de Windows (`/ZW` opción del compilador), o los destinos en tiempo de ejecución de lenguaje común (`/clr` opción del compilador).

Para obtener más información sobre los especificadores de invalidación, vea [especificador de invalidación](../cpp/override-specifier.md) y [especificadores de invalidación y compilaciones nativas](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Para obtener más información acerca de las palabras clave contextuales, vea [palabras clave contextuales](../windows/context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Ejemplos

En el ejemplo de código siguiente se muestra que **invalidar** también puede usarse en las compilaciones nativas.

```cpp
// override_keyword_1.cpp
// compile with: /c
struct I1 {
   virtual void f();
};

struct X : public I1 {
   virtual void f() override {}
};
```

### <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra que **invalidar** puede usarse en las compilaciones de Windows en tiempo de ejecución.

```cpp
// override_keyword_2.cpp
// compile with: /ZW /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Requisitos

Opción del compilador: `/ZW`

### <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra que **invalidar** puede usarse en las compilaciones en tiempo de ejecución de lenguaje común.

```cpp
// override_keyword_3.cpp
// compile with: /clr /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Requisitos

Opción del compilador: `/clr`

## <a name="see-also"></a>Vea también

[override (Especificador)](../cpp/override-specifier.md)<br/>
[Especificadores de invalidación](../windows/override-specifiers-cpp-component-extensions.md)