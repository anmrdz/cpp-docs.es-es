---
title: const_mem_fun_t (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b813128f07376d017a3ea76d6bb359db437f6f3
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100201"
---
# <a name="constmemfunt-class"></a>const_mem_fun_t (Clase)

Clase de adaptadores que permite llamar a una función miembro const que no toma ningún argumento como un objeto de función unaria cuando se inicializa con un argumento de referencia.

## <a name="syntax"></a>Sintaxis

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>Parámetros

*P. M.*<br/>
Un puntero a la función miembro de clase `Type` que se convertirá en un objeto de función.

*Pleft*<br/>
El objeto que la *Pm* función miembro se llama en.

## <a name="return-value"></a>Valor devuelto

Una función unaria adaptable.

## <a name="remarks"></a>Comentarios

La clase de plantilla almacena una copia de *Pm*, que debe ser un puntero a una función miembro de clase `Type`, en un objeto de miembro privado. Define su función miembro `operator()` para que devuelva ( `Pleft`->\* `Pm`)() **const**.

## <a name="example"></a>Ejemplo

Normalmente, no se usa el constructor de `const_mem_fun_t` directamente; la función auxiliar `mem_fun` se usa para adaptar funciones miembro. Vea [mem_fun](../standard-library/functional-functions.md#mem_fun) para obtener un ejemplo de cómo usar adaptadores de funciones miembro.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<functional>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)<br/>
