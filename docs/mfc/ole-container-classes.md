---
title: Clases de contenedor OLE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e17161340881bb53601bc04dce6f5e375f746b02
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404714"
---
# <a name="ole-container-classes"></a>Clases de contenedor OLE

Estas clases se utilizan las aplicaciones de contenedor. Ambos `COleLinkingDoc` y `COleDocument` administrar colecciones de `COleClientItem` objetos. En lugar de derivar la clase de documento de `CDocument`, deberá derivar desde `COleLinkingDoc` o `COleDocument`, dependiendo de si desea compatibilidad con enlaces a objetos incrustados en el documento.

Use un `COleClientItem` objetos para representar cada elemento OLE en el documento que está incrustado en otro documento o un vínculo a otro documento.

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
Admite la contención de documentos activos.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
Se utiliza para la implementación de documento compuesto, así como compatibilidad con contenedores básica. Actúa como un contenedor para las clases derivadas de `CDocItem`. Esta clase puede utilizarse como clase base para el contenedor de documentos y es la clase base para `COleServerDoc`.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
Una clase derivada de `COleDocument` que proporciona la infraestructura para la vinculación. Debe derivar las clases de documento para sus aplicaciones de contenedor de esta clase en lugar de desde `COleDocument` si desea admitir vínculos a objetos incrustados.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Mantiene la lista de elementos de cliente OLE que se encuentran en el control de edición enriquecida. Puede usar con [CRichEditView](../mfc/reference/cricheditview-class.md) y [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
Resumen de la clase base de `COleClientItem` y `COleServerItem`. Objetos de clases que derivan `CDocItem` representan elementos de documentos.

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
Una clase de elemento de cliente que representa el lado del cliente de la conexión a un elemento OLE incrustado o vinculado. Los elementos de cliente se derivan de esta clase.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
Proporciona acceso de cliente a un elemento almacenado en un control rich edit cuando se usa con OLE `CRichEditView` y `CRichEditDoc`.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Una excepción resultante de un error en el procesamiento de OLE. Esta clase se utiliza por contenedores y servidores.

## <a name="see-also"></a>Vea también

[Información general de clases](../mfc/class-library-overview.md)

