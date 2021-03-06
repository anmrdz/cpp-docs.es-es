---
title: condition_variable (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4d31a93ac8e0f7785ea567821c0ac6b0ad6a58
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109841"
---
# <a name="conditionvariable-class"></a>condition_variable (Clase)

Utilice la clase `condition_variable` para esperar un evento cuando tenga un `mutex` de tipo `unique_lock<mutex>`. Los objetos de este tipo pueden tener un rendimiento mejor que los objetos de tipo [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md).

## <a name="syntax"></a>Sintaxis

```cpp
class condition_variable;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[condition_variable](#condition_variable)|Construye un objeto `condition_variable`.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[native_handle](#native_handle)|Devuelve el tipo específico de la implementación que representa el identificador condition_variable.|
|[notify_all](#notify_all)|Desbloquea todos los subprocesos que están esperando el objeto `condition_variable`.|
|[notify_one](#notify_one)|Desbloquea uno de los subprocesos que están esperando el objeto `condition_variable`.|
|[Espere](#wait)|Bloquea un subproceso.|
|[wait_for](#wait_for)|Bloquea un subproceso y establece un intervalo de tiempo después del cual el subproceso se desbloquea.|
|[wait_until](#wait_until)|Bloquea un subproceso y establece un punto máximo en el tiempo en el que el subproceso se desbloquea.|

## <a name="requirements"></a>Requisitos

**Encabezado:** \<condition_variable >

**Espacio de nombres:** std

## <a name="condition_variable"></a>  condition_variable::condition_variable (Constructor)

Construye un objeto `condition_variable`.

```cpp
condition_variable();
```

### <a name="remarks"></a>Comentarios

Si no queda suficiente memoria disponible, el constructor produce un objeto [system_error](../standard-library/system-error-class.md) que tiene un código de error de `not_enough_memory`. Si el objeto no puede construirse porque algún otro recurso no está disponible, el constructor produce un objeto `system_error` que tiene un código de error de `resource_unavailable_try_again`.

## <a name="native_handle"></a>  condition_variable::native_handle

Devuelve el tipo específico de la implementación que representa el identificador condition_variable.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Valor devuelto

`native_handle_type` se define como un puntero a estructuras de datos internas del Runtime de simultaneidad.

## <a name="notify_all"></a>  condition_variable::notify_all

Desbloquea todos los subprocesos que están esperando el objeto `condition_variable`.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable::notify_one

Desbloquea uno de los subprocesos que están esperando el objeto `condition_variable`.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable::wait

Bloquea un subproceso.

```cpp
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parámetros

*Lck*<br/>
Un objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).

*Pred*<br/>
Cualquier expresión que devuelva **true** o **false**.

### <a name="remarks"></a>Comentarios

El primer método se bloquea hasta que el objeto `condition_variable` se señaliza mediante una llamada a [notify_one](#notify_one) o a [notify_all](#notify_all). También se puede reactivar en falso.

En efecto, el segundo método ejecuta el código siguiente.

```cpp
while(!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable::wait_for

Bloquea un subproceso y establece un intervalo de tiempo después del cual el subproceso se desbloquea.

```cpp
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parámetros

*Lck*<br/>
Un objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).

*Rel_time*<br/>
Objeto `chrono::duration` que especifica la cantidad de tiempo que tiene que transcurrir hasta que el subproceso se reactive.

*Pred*<br/>
Cualquier expresión que devuelva **true** o **false**.

### <a name="return-value"></a>Valor devuelto

Devuelve el primer método `cv_status::timeout` si la espera termina cuando *Rel_time* ha transcurrido. De lo contrario, el método devuelve `cv_status::no_timeout`.

El segundo método devuelve el valor de *Pred*.

### <a name="remarks"></a>Comentarios

El primer método se bloquea hasta que el `condition_variable` objeto se señaliza mediante una llamada a [notify_one](#notify_one) o [notify_all](#notify_all) o hasta que el intervalo de tiempo *Rel_time* ha transcurrido. También se puede reactivar en falso.

En efecto, el segundo método ejecuta el código siguiente.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable::wait_until

Bloquea un subproceso y establece un punto máximo en el tiempo en el que el subproceso se desbloquea.

```cpp
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parámetros

*Lck*<br/>
Un objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).

*Abs_time*<br/>
Un objeto [chrono::time_point](../standard-library/time-point-class.md).

*Pred*<br/>
Cualquier expresión que devuelva **true** o **false**.

### <a name="return-value"></a>Valor devuelto

Los métodos que devuelven un `cv_status` escriba volver `cv_status::timeout` si la espera termina cuando *Abs_time* transcurre. De lo contrario, los métodos devuelven `cv_status::no_timeout`.

Los métodos que devuelven un **bool** devolver el valor de *Pred*.

### <a name="remarks"></a>Comentarios

El primer método se bloquea hasta que el objeto `condition_variable` se señaliza mediante una llamada a [notify_one](#notify_one) o a [notify_all](#notify_all), o hasta que transcurre `Abs_time`. También se puede reactivar en falso.

En efecto, el segundo método ejecuta el código siguiente

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Los métodos tercero y cuarto utilizan un puntero a un objeto de tipo `xtime` para reemplazar el objeto `chrono::time_point`. El objeto `xtime` especifica el tiempo máximo que hay que esperar una señal.

## <a name="see-also"></a>Vea también

[Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
