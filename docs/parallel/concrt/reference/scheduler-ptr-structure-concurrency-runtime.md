---
title: scheduler_ptr (estructura) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea128a6122bf69735d118045eef2e8d8e323f8de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393426"
---
# <a name="schedulerptr-structure"></a>scheduler_ptr (estructura)

Representa un puntero a un programador. Esta clase existe para permitir la especificación de una duración compartida mediante shared_ptr o simplemente una referencia sin formato mediante un puntero sin formato.

## <a name="syntax"></a>Sintaxis

```
struct scheduler_ptr;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[scheduler_ptr::scheduler_ptr](#ctor)|Sobrecargado. Crea un puntero de programador que va de shared_ptr al programador|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[scheduler_ptr::get](#get)|Devuelve el puntero sin formato al programador|

### <a name="public-operators"></a>Operadores públicos

|Name|Descripción|
|----------|-----------------|
|[scheduler_ptr:: operator bool](#operator_bool)|Prueba si el puntero del programador no es null|
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Se comporta como un puntero|

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`scheduler_ptr`

## <a name="requirements"></a>Requisitos

**Encabezado:** pplinterface.h

**Espacio de nombres:** simultaneidad

##  <a name="get"></a>  scheduler_ptr::Get (método)

Devuelve el puntero sin formato al programador

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>Valor devuelto

##  <a name="operator_bool"></a>  scheduler_ptr:: operator bool

Prueba si el puntero del programador no es null

''' operador bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;

Behave like a pointer

```
operador de scheduler_interface () -> () const;
```

### Return Value

##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor

Creates a scheduler pointer from shared_ptr to scheduler

```
scheduler_ptr (de) explícita (scheduler std:: shared_ptr < scheduler_interface () >);

scheduler_ptr (de) explícita (_In_opt_ pScheduler scheduler_interface () *);
```

### Parameters

*scheduler*<br/>
The scheduler to convert.

*pScheduler*<br/>
The scheduler pointer to convert.

## See Also

[concurrency Namespace](concurrency-namespace.md)
