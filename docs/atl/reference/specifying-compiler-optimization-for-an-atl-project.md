---
title: Especificación de la optimización del compilador para un proyecto ATL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f756da8f553d68e89dcbee737adbab75f256ae8d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053128"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Especificación de la optimización del compilador para un proyecto ATL

De forma predeterminada, el [Asistente para controles ATL](../../atl/reference/atl-control-wizard.md) genera clases nuevas con la macro ATL_NO_VTABLE, como se indica a continuación:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

A continuación, ATL define _ATL_NO_VTABLE como sigue:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

Si no define _ATL_DISABLE_NO_VTABLE, la macro ATL_NO_VTABLE se expande a `declspec(novtable)`. Uso de `declspec(novtable)`en una clase de declaración impide que el puntero vtable que se inicializa en el constructor de clase y el destructor. Al compilar el proyecto, el vinculador eliminará vtable y todas las funciones a la que apunta la vtable.

Debe utilizar ATL_NO_VTABLE y por consiguiente `declspec(novtable)`, únicamente con clases base que no se puede crear directamente. No se debe usar `declspec(novtable)` con la clase más derivada en el proyecto, dado que esta clase (normalmente [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), o [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) Inicializa el puntero vtable para el proyecto.

No debe llamar a funciones virtuales desde el constructor de cualquier objeto que usa `declspec(novtable)`. Debe mover esas llamadas a la [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) método.

Si no está seguro de si debe utilizar el `declspec(novtable)` modificador, puede quitar la macro ATL_NO_VTABLE de cualquier definición de clase, o puede deshabilitar globalmente mediante la especificación

```
#define _ATL_DISABLE_NO_VTABLE
```

en stdafx.h, antes de todos los demás ATL, archivos de encabezado se incluyen.

## <a name="see-also"></a>Vea también

[Asistente para proyectos ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Tipos de proyecto de Visual C++](../../ide/visual-cpp-project-types.md)<br/>
[Crear proyectos de escritorio con asistentes para aplicaciones](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[Programar con ATL y código en tiempo de ejecución de C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Aspectos básicos de los objetos ATL COM](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Configuraciones de proyecto ATL predeterminadas](../../atl/reference/default-atl-project-configurations.md)

