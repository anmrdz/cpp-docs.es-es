---
title: invalid_operation (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e903a3d5e269a273a191fd733ff8813b75b53a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416918"
---
# <a name="invalidoperation-class"></a>invalid_operation (Clase)

Esta clase describe una excepción producida cuando se realiza una operación no válida que no está descrita con más precisión por otro tipo de excepción producida por el runtime de simultaneidad.

## <a name="syntax"></a>Sintaxis

```
class invalid_operation : public std::exception;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[invalid_operation](#ctor)|Sobrecargado. Construye un objeto `invalid_operation`.|

## <a name="remarks"></a>Comentarios

Los diversos métodos que producen esta excepción normalmente indicarán bajo qué circunstancias la producen.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`exception`

`invalid_operation`

## <a name="requirements"></a>Requisitos

**Encabezado:** concrt.h

**Espacio de nombres:** simultaneidad

##  <a name="ctor"></a> invalid_operation)

Construye un objeto `invalid_operation`.

```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parámetros

*_Cuerpo*<br/>
Mensaje descriptivo del error.

## <a name="see-also"></a>Vea también

[concurrency (espacio de nombres)](concurrency-namespace.md)
