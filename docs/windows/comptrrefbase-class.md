---
title: ComPtrRefBase (clase) | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79b7c3df2b6d3dc338ecda713b4ec406c8964cab
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789259"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase (clase)

Admite la infraestructura WRL y no está pensado para utilizarse directamente desde el código.

## <a name="syntax"></a>Sintaxis

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parámetros

*T*<br/>
Un [ComPtr\<T >](../windows/comptr-class.md) tipo o un tipo derivado de éste, no simplemente la interfaz representada por el `ComPtr`.

## <a name="remarks"></a>Comentarios

Representa la clase base para el [ComPtrRef](../windows/comptrref-class.md) clase.

## <a name="members"></a>Miembros

### <a name="public-typedefs"></a>Definiciones de tipos públicas

Name            | Descripción
--------------- | -------------------------------------------------
`InterfaceType` | Un sinónimo del tipo de parámetro de plantilla *T*.

### <a name="public-operators"></a>Operadores públicos

Name                                                                       | Descripción
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[Comptrrefbase:: operator IInspectable **](#operator-iinspectable-star-star) | Convierte la actual [ptr_](#ptr) miembro de datos a un puntero-a-a-puntero-to del `IInspectable` interfaz.
[Comptrrefbase:: operator IUnknown **](#operator-iunknown-star-star)         | Convierte la actual [ptr_](#ptr) miembro de datos a un puntero-a-a-puntero-to del `IUnknown` interfaz.

### <a name="protected-data-members"></a>Miembros de datos protegidos

nombre                        | Descripción
--------------------------- | ----------------------------------------------------------------
[Comptrrefbase](#ptr) | Puntero al tipo especificado por el parámetro de plantilla actual.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`ComPtrRefBase`

## <a name="requirements"></a>Requisitos

**Encabezado:** client.h

**Namespace:** wrl

## <a name="operator-iinspectable-star-star"></a>Comptrrefbase:: operator IInspectable\* \* operador

Admite la infraestructura WRL y no está pensado para utilizarse directamente desde el código.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Comentarios

Convierte la actual [ptr_](#ptr) miembro de datos a un puntero-a-a-puntero-to del `IInspectable` interfaz.

Se genera un error si el actual `ComPtrRefBase` no se deriva de `IInspectable`.

En esta difusión está disponible solo si `__WRL_CLASSIC_COM__` está definido.

## <a name="operator-iunknown-star-star"></a>Comptrrefbase:: operator IUnknown ** (operador)

Admite la infraestructura WRL y no está pensado para utilizarse directamente desde el código.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Comentarios

Convierte la actual [ptr_](#ptr) miembro de datos a un puntero-a-a-puntero-to del `IUnknown` interfaz.

Se genera un error si el actual `ComPtrRefBase` no se deriva de `IUnknown`.

## <a name="ptr"></a>Comptrrefbase

Admite la infraestructura WRL y no está pensado para utilizarse directamente desde el código.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Comentarios

Puntero al tipo especificado por el parámetro de plantilla actual. `ptr_` es el miembro de datos protegidos.
