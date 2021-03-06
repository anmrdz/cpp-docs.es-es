---
title: 'Nociones OLE: Implementación de MFC | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d6fdd0fa05ec21151a28c516adcb224f5e9b0ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409836"
---
# <a name="ole-background-mfc-implementation"></a>Nociones de OLE: Implementación de MFC

Debido al tamaño y complejidad de la API OLE sin procesar, llamarlo directamente para escribir aplicaciones OLE puede llevar mucho tiempo. El objetivo de la implementación de la biblioteca Microsoft Foundation Class de OLE es reducir la cantidad de trabajo que tiene que hacer para escribir aplicaciones completas, compatible con OLE.

En este artículo se explica las partes de la API de OLE que no se han implementado dentro de MFC. También se explica cómo se implementa lo que se asigna a la sección OLE del SDK de Windows.

##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Algunas partes de OLE no implementadas por la biblioteca de clases

Algunas interfaces y las características de OLE no se proporcionan directamente por MFC. Si desea usar estas características, puede llamar a la API de OLE directamente.

IMoniker (interfaz) el `IMoniker` interfaz se implementa mediante la biblioteca de clases (por ejemplo, el `COleServerItem` clase), pero no se haya expuesto anteriormente para el programador. Para obtener más información acerca de esta interfaz, vea implementaciones OLE Moniker en la sección OLE del SDK de Windows. Sin embargo, también vea clase [CMonikerFile](../mfc/reference/cmonikerfile-class.md) y [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

Interfaces IUnknown e IMarshal el `IUnknown` interfaz se implementa mediante la biblioteca de clases, pero no se expone al programador. El `IMarshal` interfaz no está implementado por la biblioteca de clases, pero se usa internamente. Servidores de automatización creados con la biblioteca de clases ya tienen capacidades integradas el cálculo de referencias.

Archivos compuestos DOCFILES (archivos compuestos) se admiten parcialmente por la biblioteca de clases. Ninguna de las funciones que manipulan directamente los archivos compuestos más allá de creación se admiten. MFC utiliza la clase `COleFileStream` para admitir la manipulación de secuencias con funciones estándar de archivo. Para obtener más información, vea el artículo [contenedores: archivos compuestos](../mfc/containers-compound-files.md).

Servidores en proceso y controladores de objeto de servidores en proceso y controladores de objeto permiten la implementación de la edición visual de datos o los objetos de modelo de objetos componentes (COM) completos en una biblioteca de vínculos dinámicos (DLL). Para ello, puede implementar el archivo DLL mediante una llamada a la API de OLE directamente. Sin embargo, si está escribiendo un servidor de automatización y el servidor no tiene ninguna interfaz de usuario, puede usar el Asistente para aplicaciones para que a su servidor en un servidor en proceso y colocarlo en un archivo DLL. Para obtener más información acerca de estos temas, consulte [servidores de automatización](../mfc/automation-servers.md).

> [!TIP]
>  Es la manera más fácil de implementar un servidor de automatización colocarlo en un archivo DLL. MFC es compatible con este enfoque.

Para obtener más información sobre cómo las clases OLE de Microsoft Foundation implementan interfaces OLE, vea Notas técnicas de MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), y [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="see-also"></a>Vea también

[Nociones de OLE](../mfc/ole-background.md)<br/>
[Nociones de OLE: Estrategias de implementación](../mfc/ole-background-implementation-strategies.md)

