---
title: UUID (atributos de C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3eddf1981aba8babcb87562ed546ce4086499fd7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071344"
---
# <a name="uuid-c-attributes"></a>uuid (Atributos de C++)

Especifica el identificador único para una clase o interfaz.

## <a name="syntax"></a>Sintaxis

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Parámetros

*uuid*<br/>
Un identificador de 128 bits único.

## <a name="remarks"></a>Comentarios

Si no especifica la definición de una interfaz o clase la **uuid** atributo de C++ y, a continuación, el compilador de Visual C++ proporcionará uno. Cuando se especifica un **uuid**, debe incluir las comillas.

Si no especifica **uuid**, el compilador generará el mismo GUID para las interfaces o clases con el mismo nombre en los proyectos de atributo diferente en un equipo.

Puede usar Uuidgen.exe o Guidgen.exe para generar sus propios identificadores únicos. (Para ejecutar cualquiera de estas herramientas, haga clic en **iniciar** y haga clic en **ejecutar** en el menú. A continuación, escriba el nombre de la herramienta necesaria.)

Cuando se utiliza en un proyecto que no utilizar ATL también, especificando el **uuid** atributo es el mismo que si se especifica la [uuid](../../cpp/uuid-cpp.md) **__declspec** modificador. Para recuperar el **uuid** de una clase, puede usar [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>Ejemplo

Consulte la [enlazable](bindable.md) ejemplo para un ejemplo de uso de **uuid**.

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Contexto de atributo

|||
|-|-|
|**Se aplica a**|**clase**, **struct**, **interfaz**, **unión**, **enum**|
|**Reiterativo**|No|
|**Atributos requeridos**|Ninguna|
|**Atributos no válidos**|Ninguna|

Para obtener más información acerca de los contextos de atributo, consulte [Contextos de atributo](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Vea también

[Atributos IDL](idl-attributes.md)<br/>
[Atributos de interfaz](interface-attributes.md)<br/>
[Atributos de clase](class-attributes.md)<br/>
[Typedef, Enum, Union y Struct (atributos)](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/desktop/Midl/uuid)