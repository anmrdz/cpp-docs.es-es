---
title: cache_freelist (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3d3902d900e0dad5ec3e335e9c3424d58ee2674
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960422"
---
# <a name="cachefreelist-class"></a>cache_freelist (Clase)

Define un [asignador de bloques](../standard-library/allocators-header.md) que asigna y desasigna bloques de memoria de un tamaño único.

## <a name="syntax"></a>Sintaxis

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*sz*|El número de elementos de la matriz que se van a asignar.|
|*Max*|La clase máxima que representa el tamaño máximo de la lista libre. Esta puede ser [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md) o [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Comentarios

La clase de plantilla cache_freelist mantiene una lista libre de bloques de memoria de tamaño *Sz*. Cuando la lista libre está llena utiliza **operador delete** desasignar memoria bloquea. Cuando la lista libre está vacía, usa **operador new** para asignar nuevos bloques de memoria. El tamaño máximo de la lista libre viene determinada por la clase clase máxima pasada en el *Max* parámetro.

Cada bloque de memoria contiene *Sz* bytes de memoria utilizable y los datos que **new (operador)** y **operador delete** requieren.

### <a name="constructors"></a>Constructores

|Constructor|Descripción|
|-|-|
|[cache_freelist](#cache_freelist)|Construye un objeto de tipo `cache_freelist`.|

### <a name="member-functions"></a>Funciones miembro

|Función miembro|Descripción|
|-|-|
|[allocate](#allocate)|Asigna un bloque de memoria.|
|[deallocate](#deallocate)|Libera un número especificado de objetos del almacenamiento, a partir de la posición especificada.|

## <a name="requirements"></a>Requisitos

**Encabezado:** \<allocators>

**Espacio de nombres:** stdext

## <a name="allocate"></a>  cache_freelist::allocate

Asigna un bloque de memoria.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*count*|El número de elementos de la matriz que se van a asignar.|

### <a name="return-value"></a>Valor devuelto

Un puntero al objeto asignado.

### <a name="remarks"></a>Comentarios

## <a name="cache_freelist"></a>  cache_freelist::cache_freelist

Construye un objeto de tipo `cache_freelist`.

```cpp
cache_freelist();
```

### <a name="remarks"></a>Comentarios

## <a name="deallocate"></a>  cache_freelist::deallocate

Libera un número especificado de objetos del almacenamiento, a partir de la posición especificada.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*ptr*|Un puntero al primer objeto que se va a desasignar del almacenamiento.|
|*count*|El número de objetos que se van a desasignar del almacenamiento.|

### <a name="remarks"></a>Comentarios

## <a name="see-also"></a>Vea también

[\<allocators>](../standard-library/allocators-header.md)<br/>
