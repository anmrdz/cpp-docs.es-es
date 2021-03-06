---
title: IsBaseOfStrict (estructura) | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90ceaf20a5d601fc2904b7ce8610b4a3906e30ac
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161208"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict (estructura)

Admite la infraestructura WRL y no está pensado para utilizarse directamente desde el código.

## <a name="syntax"></a>Sintaxis

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parámetros

*base*<br/>
El tipo base.

*Derivados*<br/>
El tipo derivado.

## <a name="remarks"></a>Comentarios

Comprueba si un tipo es la base de otro.

La primera plantilla comprueba si un tipo se deriva de un tipo base, que podría producir **true** o **false**. La segunda plantilla comprueba si un tipo se deriva de sí misma, que siempre produce **false**.

## <a name="members"></a>Miembros

### <a name="public-constants"></a>Constantes públicas

nombre                            | Descripción
------------------------------- | --------------------------------------------------
[Isbaseofstrict](#value) | Indica si un tipo es la base de otro.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`IsBaseOfStrict`

## <a name="requirements"></a>Requisitos

**Encabezado:** internal.h

**Namespace:** wrl

## <a name="value"></a>Isbaseofstrict

Admite la infraestructura WRL y no está pensado para utilizarse directamente desde el código.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Comentarios

Indica si un tipo es la base de otro.

`value` es **true** si tipo `Base` es una clase base del tipo `Derived`, de lo contrario es **false**.
