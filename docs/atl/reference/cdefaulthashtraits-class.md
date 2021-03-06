---
title: CDefaultHashTraits (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34aa546561e13c2728c633db3f96861a1d3ec987
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075688"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits (clase)

Esta clase proporciona una función estática para calcular los valores hash.

## <a name="syntax"></a>Sintaxis

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>Parámetros

*T*<br/>
El tipo de datos que se almacenará en la colección.

## <a name="members"></a>Miembros

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CDefaultHashTraits::Hash](#hash)|(Estático) Llame a esta función para calcular un valor hash para un elemento determinado.|

## <a name="remarks"></a>Comentarios

Esta clase contiene una sola función estática que devuelve un valor hash para un elemento determinado. Esta clase se utiliza por la [CDefaultElementTraits (clase)](../../atl/reference/cdefaultelementtraits-class.md).

Para obtener más información, consulte [clases de colección ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Requisitos

**Encabezado:** atlcoll.h

##  <a name="hash"></a>  CDefaultHashTraits::Hash

Llame a esta función para calcular un valor hash para un elemento determinado.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Parámetros

*Elemento*<br/>
El elemento.

### <a name="return-value"></a>Valor devuelto

Devuelve el valor hash.

### <a name="remarks"></a>Comentarios

El algoritmo hash predeterminado es muy sencillo: el valor devuelto es el número de elemento. Reemplace esta función si es necesario un algoritmo más complicado.

## <a name="see-also"></a>Vea también

[Información general de clases](../../atl/atl-class-overview.md)
