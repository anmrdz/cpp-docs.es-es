---
title: Aspectos básicos de los objetos ATL COM | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b90d8901a60b5945b2b29db2c378a0cd29939f63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059282"
---
# <a name="fundamentals-of-atl-com-objects"></a>Aspectos básicos de los objetos ATL COM

La siguiente ilustración muestra la relación entre las clases e interfaces que se usan para definir un objeto COM de ATL.

![Estructura ATL](../atl/media/vc307y1.gif "vc307y1")

> [!NOTE]
>  Este diagrama muestra que `CComObject` se deriva de `CYourClass` , mientras que `CComAggObject` y `CComPolyObject` incluyen `CYourClass` como una variable de miembro.

Hay tres maneras de definir un objeto COM de ATL. La opción estándar es usar el `CComObject` clase que deriva de `CYourClass`. La segunda opción consiste en crear un objeto agregado mediante el uso de la `CComAggObject` clase. La tercera opción es usar el `CComPolyObject` clase. `CComPolyObject` actúa como un híbrido: puede funcionar como un `CComObject` clase o como un `CComAggObject` (clase), dependiendo de cómo se crea por primera vez. Para obtener más información sobre cómo usar el `CComPolyObject` de clases, vea [CComPolyObject (clase)](../atl/reference/ccompolyobject-class.md).

Cuando se usa COM de ATL estándar, use dos objetos: un objeto externo y un objeto interno. Los clientes externos acceso a la funcionalidad del objeto interno a través de las funciones de contenedor que se definen en el objeto externo. El objeto externo es de tipo `CComObject`.

Cuando se usa un objeto agregado, el objeto externo no proporciona contenedores para la funcionalidad del objeto interno. En su lugar, el objeto externo proporciona un puntero que se accede directamente por los clientes externos. En este escenario, el objeto externo es de tipo `CComAggObject`. El objeto interno es una variable de miembro del objeto externo, y es de tipo `CYourClass`.

Dado que el cliente no tiene que pasar por el objeto externo para interactuar con el objeto interno, los objetos agregados son suele ser más eficaces. Además, el objeto externo no debe conocer la funcionalidad del objeto agregado, dado que la interfaz del objeto agregado está disponible directamente al cliente. Sin embargo, no todos los objetos se pueden agregar. Se puede agregar un objeto, debe diseñarse con la agregación en mente.

ATL implementa [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) en dos fases:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), o [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementa el `IUnknown` métodos.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) o [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) administra el recuento de referencias y los punteros externos de `IUnknown`.

Otros aspectos de su objeto ATL COM son controlados por otras clases:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) define el modelo de fábrica y agregación de la clase del predeterminado del objeto.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) proporciona una implementación predeterminada de la `IDispatch Interface` parte de las interfaces duales en el objeto.

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) implementa el `ISupportErrorInfo` interfaz que garantiza la información de error se puede propagar en la cadena de llamada correctamente.

## <a name="in-this-section"></a>En esta sección

[Implementar CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)<br/>
Mostrar entradas de mapa COM para la implementación de ejemplo `CComObjectRootEx`.

[Implementar CComObject, CComAggObject y CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
Describe cómo el **DECLARE_\*_AGGREGATABLE** macros afectan el uso de `CComObject`, `CComAggObject`, y `CComPolyObject`.

[Admitir IDispatch e IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
Enumera las clases de implementación ATL que se usará para admitir la `IDispatch` y `IErrorInfo` interfaces.

[Admitir IDispEventImpl](../atl/supporting-idispeventimpl.md)<br/>
Describe los pasos para implementar un punto de conexión para la clase.

[Cambiar el generador de clases predeterminado y el modelo de agregación](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Muestra qué macros a usar para cambiar el modelo de fábrica y agregación de clase predeterminado.

[Crear un objeto agregado](../atl/creating-an-aggregated-object.md)<br/>
Se enumeran los pasos para crear un objeto agregado.

## <a name="related-sections"></a>Secciones relacionadas

[Creación de un proyecto ATL](../atl/reference/creating-an-atl-project.md)<br/>
Proporciona información sobre cómo crear un objeto COM de ATL.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Proporciona vínculos a temas sobre cómo programar utilizando Active Template Library.

## <a name="see-also"></a>Vea también

[Conceptos](../atl/active-template-library-atl-concepts.md)

