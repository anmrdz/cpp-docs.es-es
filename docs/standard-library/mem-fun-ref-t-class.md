---
title: Clase mem_fun_ref_t | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dffdb71b8121073775af52ed42cda205c70589
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100175"
---
# <a name="memfunreft-class"></a>mem_fun_ref_t (Clase)

Clase de adaptadores que permite un `non_const` función miembro que no toma ningún argumento como un objeto de función unaria cuando se inicializa con un argumento de referencia.

## <a name="syntax"></a>Sintaxis

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;

};
```

### <a name="parameters"></a>Parámetros

*_Pm*<br/>
Un puntero a la función miembro de clase `Type` que se convertirá en un objeto de función.

*left*<br/>
El objeto que la *_Pm* función miembro se llama en.

## <a name="return-value"></a>Valor devuelto

Una función unaria adaptable.

## <a name="remarks"></a>Comentarios

La clase de plantilla almacena una copia de *_Pm*, que debe ser un puntero a una función miembro de clase `Type`, en un objeto de miembro privado. Define su función miembro `operator()` para que devuelva ( **left**.* `_Pm`)( ).

## <a name="example"></a>Ejemplo

Normalmente, no se usa el constructor de `mem_fun_ref_t` directamente; la función auxiliar `mem_fun_ref` se usa para adaptar funciones miembro. Vea [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) para obtener un ejemplo de cómo usar adaptadores de funciones miembro.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<functional>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)<br/>
