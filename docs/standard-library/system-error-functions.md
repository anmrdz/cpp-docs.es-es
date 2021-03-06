---
title: Funciones de &lt;system_error&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 838a63fc43ef71561c0911cfa4c85c76cf04bc08
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959670"
---
# <a name="ltsystemerrorgt-functions"></a>Funciones de &lt;system_error&gt;

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a>  generic_category

Representa la categoría de errores genéricos.

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>Comentarios

El `generic_category` objeto es una implementación de [error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a>  make_error_code

Crea un objeto de código de error.

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*_Errno*|El valor de enumeración que se va a almacenar en el objeto de código de error.|

### <a name="return-value"></a>Valor devuelto

El objeto de código de error.

### <a name="remarks"></a>Comentarios

## <a name="make_error_condition"></a>  make_error_condition

Crea un objeto de la condición de error.

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*_Errno*|El valor de enumeración que se va a almacenar en el objeto de la condición de error.|

### <a name="return-value"></a>Valor devuelto

El objeto de la condición de error.

### <a name="remarks"></a>Comentarios

## <a name="system_category"></a>  system_category

Representa la categoría de los errores causados por desbordamientos del sistema de bajo nivel.

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>Comentarios

El `system_category` objeto es una implementación de [error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Vea también

[<system_error>](../standard-library/system-error.md)<br/>
