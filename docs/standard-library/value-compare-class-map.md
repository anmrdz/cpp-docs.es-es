---
title: value_compare (Clase) (&lt;asignación&gt;) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46f8d00877aa4147e4b3e4ec2a6a23b70d8154c8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965853"
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare (Clase) (&lt;asignación&gt;)

Proporciona un objeto de función que puede comparar los elementos de una asignación comparando los valores de sus claves para determinar su orden relativo en la asignación.

## <a name="syntax"></a>Sintaxis

```cpp
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```

## <a name="remarks"></a>Comentarios

El criterio de comparación proporcionado por `value_compare` entre `value_types` de elementos enteros incluidos en una asignación se induce de una comparación entre las claves de los respectivos elementos mediante la construcción de la clase auxiliar. El operador de la función miembro usa el objeto `comp` typu `key_compare` almacenados en el objeto de función proporcionado por `value_compare` para comparar los componentes clave de ordenación de dos elementos.

Para conjuntos y conjuntos múltiples, que son simples contenedores donde los valores de clave son idénticos a los valores de elemento, `value_compare` es equivalente a `key_compare`. No lo es para asignaciones y asignaciones múltiples, dado que el valor de los elementos de tipo `pair` no es idéntico al valor de clave del elemento.

## <a name="example"></a>Ejemplo

Vea el ejemplo de [value_comp](../standard-library/map-class.md#value_comp) para obtener un ejemplo de cómo declarar y usar `value_compare`.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<map>

**Espacio de nombres:** std

## <a name="see-also"></a>Vea también

[binary_function (Struct)](../standard-library/binary-function-struct.md)<br/>
[Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referencia de biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)<br/>
