---
title: Compilador advertencia (nivel 1) C4436 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2484b5420347f49a74d8eb3cdf65a8221741cc63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076507"
---
# <a name="compiler-warning-level-1-c4436"></a>Advertencia del compilador (nivel 1) C4436

dynamic_cast de la base virtual 'clase1' a 'clase2' en el constructor o destructor podría producir un error con objetos construidos parcialmente compilar con/vd2 o defina 'clase2' con #pragma vtordisp (2) en vigor

El compilador ha encontrado un `dynamic_cast` operación con las siguientes características.

- La conversión es desde un puntero de clase base a un puntero de la clase derivada.

- La clase derivada hereda virtualmente la clase base.

- La clase derivada no tiene un `vtordisp` campo para la base virtual.

- La conversión se encuentra en un constructor o destructor de la clase derivada, o alguna clase que más se hereda de la clase derivada.

La advertencia que indica el `dynamic_cast` es posible que no funcionen correctamente, si se está ejecutando en un objeto parcialmente construido.  Esto sucede si el constructor o destructor derivado está funcionando en un objeto secundario de algún objeto más derivado.  Si la clase derivada denominada en la advertencia nunca es más derivado, puede omitir la advertencia.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C4436 y muestra el problema de generación de código que se origina desde el que falta `vtordisp` campo.

```cpp
// C4436.cpp
// To see the warning and runtime assert, compile with: /W1
// To eliminate the warning and assert, compile with: /W1 /vd2
//       or compile with: /W1 /DFIX
#include <cassert>

struct A
{
public:
    virtual ~A() {}
};

#if defined(FIX)
#pragma vtordisp(push, 2)
#endif
struct B : virtual A
{
    B()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4436
        assert(this == b);              // assert unless compiled with /vd2
    }
};
#if defined(FIX)
#pragma vtordisp(pop)
#endif

struct C : B
{
    int i;
};

int main()
{
    C c;
}
```

## <a name="see-also"></a>Vea también

[dynamic_cast (Operador)](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Advertencia del compilador (nivel 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)