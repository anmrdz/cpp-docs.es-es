---
title: CComAutoCriticalSection (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40fa13ecf743bf8e6aa0cd75b16bec65131fe267
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061084"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection (clase)

`CComAutoCriticalSection` Proporciona métodos para obtener y liberar la propiedad de un objeto de sección crítica.

## <a name="syntax"></a>Sintaxis

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|El constructor.|
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Destructor.|

## <a name="remarks"></a>Comentarios

`CComAutoCriticalSection` es similar a la clase [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), excepto `CComAutoCriticalSection` automáticamente inicializa el objeto de sección crítica en el constructor.

Normalmente, se utiliza `CComAutoCriticalSection` a través de la `typedef` nombre [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Este nombre hace referencia a `CComAutoCriticalSection` cuando [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) se está usando.

El `Init` y `Term` métodos desde [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) no están disponibles cuando se usa esta clase.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Requisitos

**Encabezado:** atlcore.h

##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection

El constructor.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Comentarios

Llama a la función de Win32 [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), que inicializa el objeto de sección crítica.

##  <a name="dtor"></a>  CComAutoCriticalSection:: ~ CComAutoCriticalSection

Destructor.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Comentarios

El destructor llama a [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), que libera todos los recursos del sistema utilizados por el objeto de sección crítica.

## <a name="see-also"></a>Vea también

[CComFakeCriticalSection (clase)](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Información general de clases](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection (clase)](../../atl/reference/ccomcriticalsection-class.md)
