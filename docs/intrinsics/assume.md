---
title: __assume | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __assume
- _assume
- __assume_cpp
dev_langs:
- C++
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41542065a4fc7d3b90fd3159dca4c7a7d169c115
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163678"
---
# <a name="assume"></a>__assume

**Específicos de Microsoft**

Pasa una sugerencia al optimizador.

## <a name="syntax"></a>Sintaxis

```
__assume(
   expression
)
```

#### <a name="parameters"></a>Parámetros

*Expresión*<br/>
Cualquier expresión que se supone que se evalúa como verdadera.

## <a name="remarks"></a>Comentarios

El optimizador supone que la condición representada por `expression` es verdadera en el punto donde aparece la palabra clave y sigue siendo verdadera hasta que se modifica `expression` (por ejemplo, mediante la asignación a una variable). El uso selectivo de las sugerencias que `__assume` pasa al optimizador puede mejorar la optimización.

Si la instrucción `__assume` se escribe como una contradicción (es decir, una expresión que siempre se evalúa como falsa), siempre se trata como `__assume(0)`. Si el código no se comporta como se esperaba, asegúrese de que la `expression` que ha definido es válida y verdadera, como se describió anteriormente. Para obtener más información sobre el comportamiento `__assume(0)` esperado, vea la sección Comentarios más adelante.

> [!WARNING]
>  Un programa no debe contener una instrucción `__assume` no válida en una ruta accesible. Si el compilador puede acceder a una instrucción `__assume` no válida, el programa podría ocasionar un comportamiento impredecible y potencialmente peligroso.

`__assume` no es un auténtico intrínseco. No tiene que declararse como una función y no se puede utilizar en una directiva `#pragma intrinsic`. Aunque no se genera ningún código, el código generado por el optimizador se ve afectado.

Use `__assume` en un [ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) solo cuando la aserción no es recuperable. No utilice `__assume` en una aserción que tenga código de recuperación de errores posterior, ya que el compilador podría optimizar el código de control de errores.

La instrucción `__assume(0)` es un caso especial. Utilice `__assume(0)` para indicar una ruta de acceso de código que no está disponible. En el ejemplo siguiente se muestra cómo utilizar `__assume(0)` para indicar que no se puede alcanzar el caso predeterminado de una instrucción switch. Muestra el uso más típico de `__assume(0)`.

Para ofrecer compatibilidad con versiones anteriores, **_assume** es un sinónimo de **__assume** a menos que la opción de compilador [/Za \(deshabilitar extensiones de lenguaje)](../build/reference/za-ze-disable-language-extensions.md) es especificado.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__assume`|x86, ARM, x64|

## <a name="example"></a>Ejemplo

```
// compiler_intrinsics__assume.cpp
#ifdef DEBUG
# define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__) )
#else
# define ASSERT(e)    ( __assume(e) )
#endif

void func1(int i)
{
}

int main(int p)
{
   switch(p){
      case 1:
         func1(1);
         break;
      case 2:
         func1(-1);
         break;
      default:
         __assume(0);
            // This tells the optimizer that the default
            // cannot be reached. As so, it does not have to generate
            // the extra code to check that 'p' has a value
            // not represented by a case arm. This makes the switch
            // run faster.
   }
}
```

El uso de `__assume(0)` indica al optimizador que no se puede alcanzar el caso predeterminado. El ejemplo demuestra que el programador sabe que las únicas entradas posibles para `p` son 1 o 2. Si se pasa otro valor para `p`, el programa deja de ser válido y provoca un comportamiento impredecible.

Como resultado de la instrucción `__assume(0)`, el compilador no genera código para comprobar si `p` tiene un valor que no está representado en una instrucción Case. Para que esto funcione, la instrucción `__assume(0)` debe ser la primera instrucción en el cuerpo del caso predeterminado.

Dado que el compilador genera código basado en `__assume`, dicho código podría no funcionar correctamente si la expresión de la instrucción `__assume` es falsa en tiempo de ejecución. Si no está seguro de que la expresión siempre será verdadera en tiempo de ejecución, puede utilizar la función `assert` para proteger el código

```
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

Desgraciadamente, este uso de `assert` impide que el compilador realice la optimización del caso predeterminado que se ha descrito anteriormente en este documento. Como alternativa, puede utilizar una macro independiente, como se indica a continuación.

```
#ifdef DEBUG
# define NODEFAULT   ASSERT(0)
#else
# define NODEFAULT   __assume(0)
#endif

   default:
      NODEFAULT;
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)<br/>
[Palabras clave](../cpp/keywords-cpp.md)