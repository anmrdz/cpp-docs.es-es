---
title: CAtlException (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56038ffe4c6062422ea34a439e73b0d90a37cfb8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097736"
---
# <a name="catlexception-class"></a>CAtlException (clase)

Esta clase define una excepción de ATL.

## <a name="syntax"></a>Sintaxis

```
class CAtlException
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|El constructor.|

### <a name="public-operators"></a>Operadores públicos

|Name|Descripción|
|----------|-----------------|
|[CAtlException::operator HRESULT](#operator_hresult)|Convierte el objeto actual en un valor HRESULT.|

### <a name="public-data-members"></a>Miembros de datos públicos

|Name|Descripción|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|La variable de tipo HRESULT creado por el objeto y se usa para almacenar la condición de error.|

## <a name="remarks"></a>Comentarios

Un `CAtlException` objeto representa una condición de excepción relacionada con una operación de ATL. La `CAtlException` clase incluye un miembro de datos públicos que almacena el código de estado que indica el motivo de la excepción y un operador de conversión que permite tratar la excepción como si fuese un HRESULT.

En general, llamará `AtlThrow` en lugar de crear un `CAtlException` objeto directamente.

## <a name="requirements"></a>Requisitos

**Encabezado:** atlexcept.h

##  <a name="catlexception"></a>  CAtlException::CAtlException

El constructor.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Parámetros

*recursos humanos*<br/>
El código de error HRESULT.

##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT

Convierte el objeto actual en un valor HRESULT.

```
operator HRESULT() const throw ();
```

##  <a name="m_hr"></a>  CAtlException::m_hr

El miembro de datos HRESULT.

```
HRESULT m_hr;
```

### <a name="remarks"></a>Comentarios

El miembro de datos que almacena la condición de error. El valor HRESULT es establecido por el constructor, [CAtlException::CAtlException](#catlexception).

## <a name="see-also"></a>Vea también

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Información general de clases](../../atl/atl-class-overview.md)
