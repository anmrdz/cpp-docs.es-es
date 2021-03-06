---
title: type_info (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- type_info
dev_langs:
- C++
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d5a44a59b8c9fcacbef5a3dff0391949869790a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104132"
---
# <a name="typeinfo-class"></a>type_info (Clase)

El **type_info** clase describe la información de tipo generada dentro del programa por el compilador. Los objetos de esta clase almacenan de forma eficaz un puntero a un nombre para el tipo. El **type_info** clase también almacena un valor codificado adecuado para comparar dos tipos de igualdad u orden de intercalación. Las reglas de codificación y la secuencia de intercalación para tipos no se especifican y pueden diferir entre programas.

El `<typeinfo>` archivo de encabezado debe incluirse para utilizar el **type_info** clase. La interfaz para el **type_info** clase es:

```cpp
class type_info {
public:
    virtual ~type_info();
    size_t hash_code() const
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

No se puede crear instancias de objetos de la **type_info** clase directamente, porque la clase tiene solo un constructor de copias privado. La única manera de construir un (temporal) **type_info** objeto consiste en usar el [typeid](../cpp/typeid-operator.md) operador. Puesto que el operador de asignación también es privado, no puede copiar ni asignar objetos de clase **type_info**.

`type_info::hash_code` define una función hash adecuada para asignar valores de tipo **typeinfo** a una distribución de valores de índice.

Los operadores `==` y `!=` puede usarse para comparar la igualdad y desigualdad con otros **type_info** objetos, respectivamente.

No hay ningún vínculo entre el orden de intercalación de tipos y las relaciones de herencia. Use el `type_info::before` para determinar la secuencia de intercalación de tipos de función miembro. No hay ninguna garantía de que `type_info::before` producirá el mismo resultado en programas diferentes o incluso ejecuciones diferentes del mismo programa. De esta manera, `type_info::before` es similar a la dirección del `(&)` operador.

El `type_info::name` función miembro devuelve un `const char*` en una cadena terminada en null que representa el nombre del tipo de lenguaje natural. La memoria a la que se señala se almacena en caché y nunca debe desasignarse directamente.

El `type_info::raw_name` función miembro devuelve un `const char*` en una cadena terminada en null que representa el nombre representativo del tipo de objeto. El nombre se almacena realmente en forma representativa para ahorrar espacio. Por lo tanto, esta función es más rápida que `type_info::name` porque no es necesario quitar el nombre de la decoración. La cadena devuelta por la `type_info::raw_name` función es útil en operaciones de comparación, pero no es legible. Si tiene una cadena legible, use el `type_info::name` funcione en su lugar.

Información de tipo se genera para sólo si de las clases polimórficas el [/GR (habilitar información de tipo en tiempo de ejecución)](../build/reference/gr-enable-run-time-type-information.md) se especificó la opción del compilador.

## <a name="see-also"></a>Vea también

[Información de tipos en tiempo de ejecución](../cpp/run-time-type-information.md)