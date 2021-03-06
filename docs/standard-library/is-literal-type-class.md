---
title: Clase is_literal_type | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd4481be124cbcbba04f6b45b4c5a08beb34f04d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103310"
---
# <a name="isliteraltype-class"></a>Clase is_literal_type

Comprueba si un tipo se puede usar como una variable `constexpr` o si se puede construir, usar o devolver desde funciones `constexpr`.

## <a name="syntax"></a>Sintaxis

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parámetros

*T*<br/>
Tipo que se va a consultar.

## <a name="remarks"></a>Comentarios

Una instancia del predicado de tipo contiene true si el tipo *T* es un *tipo literal*, en caso contrario, es false. Un tipo literal es **void**, un tipo escalar, un tipo de referencia, una matriz de tipo literal o un tipo de clase literal. Un tipo de clase literal es un tipo de clase que tiene un destructor trivial, es o bien un tipo de agregado o bien contiene al menos un constructor `constexpr` que no es de movimiento y no es de copia, y todas sus clases base y miembros de datos no estáticos son tipos literales no volátiles. Aunque el tipo de un literal es siempre un tipo literal, el concepto de tipo literal incluye todo lo que el compilador evalúe como `constexpr` en tiempo de compilación.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<type_traits>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[<type_traits>](../standard-library/type-traits.md)<br/>
