---
title: constexpr (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 150179fc0fd97450ba805d6957f5282bfaf8345c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071263"
---
# <a name="constexpr-c"></a>constexpr (C++)

La palabra clave **constexpr** se introdujo en C ++ 11 y se mejoró en C ++ 14. Significa *expresión constante*. Al igual que **const**, pueden aplicarse a las variables para que se generará un error del compilador si cualquier código intenta modificar el valor. A diferencia de **const**, **constexpr** también pueden aplicarse a las funciones y los constructores de clase. **constexpr** indica que el valor o valor devuelto, es constante y, si es posible, se calculará en tiempo de compilación.

Un **constexpr** valor integral puede usarse siempre que sea un entero const se requiere, como en los argumentos de plantilla y las declaraciones de matriz. Y cuando un valor se puede calcular en tiempo de compilación en lugar de tiempo de ejecución, puede ayudar a su programa ejecute más rápido y utiliza menos memoria.

Para limitar la complejidad de la informática constantes en tiempo de compilación y su posible impacto en tiempo de compilación, la C ++ 14 estándar requiere que los tipos implicados en expresiones constantes estén restringidos a [tipos literales](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="syntax"></a>Sintaxis

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>Parámetros

*params*<br/>
Uno o varios parámetros que deben ser un tipo literal y sí deben ser una expresión constante.

## <a name="return-value"></a>Valor devuelto

Una función o variable constexpr debe devolver un [tipo literal](trivial-standard-layout-and-pod-types.md#literal_types).

## <a name="constexpr-variables"></a>Variables constexpr

La principal diferencia entre las variables const y constexpr reside en que la inicialización de una variable const puede aplazarse hasta el tiempo de ejecución, mientras que una variable constexpr debe inicializarse en tiempo de compilación.  Todas las variables constexpr son const.

- Se puede declarar una variable con **constexpr**, si tiene un tipo de literal y se ha inicializado. Si un constructor realiza la inicialización, el constructor debe declararse como **constexpr**.

- Una referencia puede declararse como constexpr si el objeto al que hace referencia se ha inicializado mediante una expresión constante y todas las conversiones implícitas que se invoquen durante la inicialización son también expresiones constantes.

- Todas las declaraciones de una **constexpr** variable o función debe tener el **constexpr** especificador.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> funciones constexpr

Un **constexpr** función es uno cuyo valor devuelto se puede calcular en compilación cuando el código usado lo requiere.  Cuando sus argumentos son **constexpr** valores y el código usado requiere el valor devuelto en tiempo de compilación, por ejemplo, para inicializar un **constexpr** variable o proporcionar un argumento de plantilla sin tipo, se produce una constante de tiempo de compilación. Cuando se llama con los que no sean de**constexpr** argumentos, o cuando su valor no se requiere en tiempo de compilación, genera un valor en tiempo de ejecución como una función normal.  (Este doble comportamiento le evita tener que escribir **constexpr** y no-**constexpr** versiones de la misma función.)

Un **constexpr** función o el constructor es implícitamente **inline**.

Las siguientes reglas se aplican a las funciones de constexpr:

- Un **constexpr** función debe aceptar y devolver sólo [tipos literales](trivial-standard-layout-and-pod-types.md#literal_types).

- Un **constexpr** función puede ser recursivos.

- No puede ser [virtual](../cpp/virtual-cpp.md). A un constructor no puede definirse como constexpr si la clase envolvente tiene alguna clase base virtual.

- El cuerpo se puede definir como `= default` o `= delete`.

- El cuerpo puede contener ningún **goto** instrucciones o bloques try.

- Se puede declarar una especialización explícita de una plantilla que no sea constexpr como **constexpr**:

- Una especialización explícita de un **constexpr** plantilla no tiene que ser también **constexpr**:

Las siguientes reglas se aplican a **constexpr** funciones en Visual Studio 2017 y versiones posteriores:

- Puede contener **si** y **cambiar** instrucciones y todas las instrucciones bucles incluidos **para**, basado en rango, **mientras**y **hacer-mientras**.

- Puede contener declaraciones de variable local, pero se debe inicializar la variable, debe ser un tipo literal y no puede ser estáticas o locales del subproceso. La variable local declarada por no tiene que ser const y es posible que se modifique.

- No tiene una función de miembro no estática constexpr sea const de forma implícita.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Nota: En el depurador de Visual Studio, cuando la depuración no optimizada depurar la compilación, puede indicar si un **constexpr** función se evalúa en tiempo de compilación colocando un punto de interrupción dentro de él. Si se alcanza el punto de interrupción, significa que se llamó a la función en tiempo de ejecución.  En caso contrario, significa que se llamó a la función en tiempo de compilación.

## <a name="extern-constexpr"></a>extern constexpr

El [/Zc: externconstexpr](../build/reference/zc-externconstexpr.md) opción del compilador hace que el compilador aplique [vinculación externa]() a las variables declaradas con **extern constexpr**. En versiones anteriores de Visual Studio y de forma predeterminada o si **/Zc:externConstexpr-** se especifica, Visual Studio aplica vinculación interna a **constexpr** aunque se utilicen las variables del **extern** se utiliza la palabra clave. El **/Zc: externconstexpr** opción está disponible a partir de Visual Studio 2017 15.6 de actualización. y está desactivada de forma predeterminada. El /permissive-option no permite/Zc: externconstexpr.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra **constexpr** un tipo definido por el usuario, funciones y variables. Tenga en cuenta que en la última instrucción en main(), la **constexpr** función miembro GetValue() es una llamada en tiempo de ejecución porque el valor no es necesario que se conoce en tiempo de compilación.

```cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    //foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    //Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    //Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}
```

## <a name="requirements"></a>Requisitos

Visual Studio 2015

## <a name="see-also"></a>Vea también

[Declaraciones y definiciones](../cpp/declarations-and-definitions-cpp.md)<br/>
[const](../cpp/const-cpp.md)
