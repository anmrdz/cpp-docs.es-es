---
title: CSecurityAttributes (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs:
- C++
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 672da1c98ebc51a7440e29234950be2adb5e1c0e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093075"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes (clase)

Esta clase es un contenedor fino para la estructura de los atributos de seguridad.

> [!IMPORTANT]
>  Esta clase y sus miembros no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.

## <a name="syntax"></a>Sintaxis

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|El constructor.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CSecurityAttributes:: Set](#set)|Llame a este método para establecer los atributos de la `CSecurityAttributes` objeto.|

## <a name="remarks"></a>Comentarios

El `SECURITY_ATTRIBUTES` estructura contiene un [descriptor de seguridad](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) utilizado para la creación de un objeto y especifica si el identificador recuperado especificando esta estructura es heredable.

Para obtener una introducción al modelo de control de acceso en Windows, consulte [Control de acceso](/windows/desktop/SecAuthZ/access-control) en el SDK de Windows.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Requisitos

**Encabezado:** atlsecurity.h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

El constructor.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parámetros

*rSecurityDescriptor*<br/>
Referencia a un descriptor de seguridad.

*bInheritsHandle*<br/>
Especifica si se hereda el identificador devuelto cuando se crea un nuevo proceso. Si este miembro es true, el nuevo proceso hereda el identificador.

##  <a name="set"></a>  CSecurityAttributes:: Set

Llame a este método para establecer los atributos de la `CSecurityAttributes` objeto.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parámetros

*rSecurityDescriptor*<br/>
Referencia a un descriptor de seguridad.

*bInheritHandle*<br/>
Especifica si se hereda el identificador devuelto cuando se crea un nuevo proceso. Si este miembro es true, el nuevo proceso hereda el identificador.

### <a name="remarks"></a>Comentarios

Este método se usa el constructor para inicializar el `CSecurityAttributes` objeto.

## <a name="see-also"></a>Vea también

[Ejemplo de seguridad](../../visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)<br/>
[descriptor de seguridad](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Información general de clases](../../atl/atl-class-overview.md)<br/>
[Funciones globales de seguridad](../../atl/reference/security-global-functions.md)
