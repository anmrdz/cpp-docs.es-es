---
title: invalid_scheduler_policy_thread_specification (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc0f52bc36157bcbc1e6adaa28f786a01ac05263
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404922"
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification (Clase)

Esta clase describe una excepción que se produce cuando se realiza un intento para establecer los límites de simultaneidad de un objeto `SchedulerPolicy`, de tal forma que el valor de la clave `MinConcurrency` es menor que el valor de la clave `MaxConcurrency`.

## <a name="syntax"></a>Sintaxis

```
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-value-class.md#ctor|Sobrecargado. Construye un objeto `invalid_scheduler_policy_value`.|

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>Requisitos

**Encabezado:** concrt.h

**Espacio de nombres:** simultaneidad
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification)

Construye un objeto `invalid_scheduler_policy_value`.

```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>Parámetros

*_Cuerpo*<br/>
Mensaje descriptivo del error.

## <a name="see-also"></a>Vea también

[concurrency (espacio de nombres)](concurrency-namespace.md)<br/>
[SchedulerPolicy (clase)](schedulerpolicy-class.md)
