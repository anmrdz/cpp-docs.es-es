---
title: Especificador final | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e382bd75a734b205389b83455e3ab020f54ca6d3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066237"
---
# <a name="final-specifier"></a>final (especificador)

Puede usar el **final** palabra clave para designar funciones virtuales que no puede invalidarse en una clase derivada. También puede utilizarla para designar clases que no se pueden heredar.

## <a name="syntax"></a>Sintaxis

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>Comentarios

**final** es contextual y tiene un significado especial solo cuando se usa después de una declaración de función o nombre de clase; en caso contrario, no es una palabra clave reservada.

Cuando **final** se utiliza en declaraciones de clase, `base-classes` es una parte opcional de la declaración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa el **final** palabra clave para especificar que no se puede invalidar una función virtual.

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

Para obtener información sobre cómo especificar que se pueden invalidar las funciones miembro, vea [especificador de invalidación](../cpp/override-specifier.md).

El ejemplo siguiente se usa el **final** palabra clave para especificar que una clase no puede heredarse.

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>Vea también

[Palabras clave](../cpp/keywords-cpp.md)<br/>
[override (Especificador)](../cpp/override-specifier.md)