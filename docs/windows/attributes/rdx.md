---
title: RDX (atributo de COM de C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e48d71ace613eac040f83023f70f2a1f28d09f6e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082313"
---
# <a name="rdx"></a>rdx

Crea una clave del registro o modifica una clave del registro existente.

## <a name="syntax"></a>Sintaxis

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Parámetros

*key*<br/>
El nombre de la clave que se crea o se abre.

*VALUENAME*<br/>
(Opcional) Especifica el campo de valor debe establecerse. Si un campo de valor con este nombre no existe en la clave, se agrega.

*regtype*<br/>
El tipo de clave del registro que se va a agregar. Puede ser uno de los siguientes: `text`, `dword`, `binary`, o `CString`.

## <a name="remarks"></a>Comentarios

El **rdx** atributo de C++ crea o modifica una clave del registro existente para un componente COM. El atributo agrega una macro BEGIN_RDX_MAP al objeto que implementa al miembro de destino. `RegistryDataExchange`, una función insertada como resultado de la macro BEGIN_RDX_MAP, se puede usar para transferir datos entre el registro y los miembros de datos

Este atributo se puede usar junto con el [coclase](coclass.md), [progid](progid.md), o [vi_progid](vi-progid.md) atributos u otros atributos que implique uno de estos.

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Contexto de atributo

|||
|-|-|
|**Se aplica a**|**clase** o **struct** miembro|
|**Reiterativo**|No|
|**Atributos requeridos**|Ninguna|
|**Atributos no válidos**|Ninguna|

Para obtener más información acerca de los contextos de atributo, consulte [Contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Ejemplo

El código siguiente agrega una clave del Registro llamada MyValue al sistema que describe el componente COM CMyClass.

```cpp
// cpp_attr_ref_rdx.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include "atlbase.h"

[module (name="MyLib")];

class CMyClass {
public:
   CMyClass() {
      strcpy_s(m_sz, "SomeValue");
   }

   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]
   char m_sz[256];
};
```

## <a name="see-also"></a>Vea también

[Atributos COM](com-attributes.md)<br/>
[registration_script](registration-script.md)