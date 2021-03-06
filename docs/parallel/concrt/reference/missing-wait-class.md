---
title: missing_wait (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0363b7dd1e4840b7afb6c013c5d439e64fbbb2ef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425904"
---
# <a name="missingwait-class"></a>missing_wait (Clase)

Esta clase describe una excepción que se produce cuando todavía existen tareas programadas para un objeto `task_group` o `structured_task_group` en el momento que el destructor de objeto se ejecuta. Nunca se producirá esta excepción si el destructor se alcanza debido al desenredo de pila como el resultado de una excepción.

## <a name="syntax"></a>Sintaxis

```
class missing_wait : public std::exception;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[missing_wait)](#ctor)|Sobrecargado. Construye un objeto `missing_wait`.|

## <a name="remarks"></a>Comentarios

Ausencia de flujo de excepciones, usted es responsable de una llamada a la `wait` o `run_and_wait` método de un `task_group` o `structured_task_group` objeto antes de permitir que ese objeto se destruya. El runtime produce esta excepción como una indicación de que se olvidó de llamar el `wait` o `run_and_wait` método.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`exception`

`missing_wait`

## <a name="requirements"></a>Requisitos

**Encabezado:** concrt.h

**Espacio de nombres:** simultaneidad

##  <a name="ctor"></a> missing_wait)

Construye un objeto `missing_wait`.

```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parámetros

*_Cuerpo*<br/>
Mensaje descriptivo del error.

## <a name="see-also"></a>Vea también

[concurrency (espacio de nombres)](concurrency-namespace.md)<br/>
[task_group (clase)](task-group-class.md)<br/>
[Espere](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group (clase)](structured-task-group-class.md)
