---
title: Creación de nuevos documentos, Windows y vistas | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b4ccddbed0d347468331218614cad70cfd49a62
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427243"
---
# <a name="creating-new-documents-windows-and-views"></a>Crear nuevos documentos, ventanas y vistas

Las ilustraciones siguientes ofrecen información general del proceso de creación de documentos, vistas y ventanas de marco. Otros artículos que se centran en los objetos participantes proporcionan más detalles.

Tras la finalización de este proceso, los objetos en colaboración existen y almacenan punteros a entre sí. Las ilustraciones siguientes muestran la secuencia en que se crean los objetos. Puede seguir la secuencia de una ilustración a otra.

![Secuencia para crear un documento](../mfc/media/vc387l1.gif "vc387l1") secuencia de creación de un documento

![Secuencia de creación de ventanas de marco](../mfc/media/vc387l2.png "vc387l2") secuencia de creación de una ventana de marco

![Secuencia para crear una vista](../mfc/media/vc387l3.gif "vc387l3") secuencia de creación de una vista

Para obtener información acerca de cómo el marco de trabajo inicializa el nuevo documento, vista y los objetos de ventana de marco, vea clases [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), y [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) en la referencia de la biblioteca MFC. Consulte también [Nota técnica 22](../mfc/tn022-standard-commands-implementation.md), que explica los procesos de creación e inicialización adicional en su discusión de los comandos estándar de .NET framework para la **New** y **abrir** los elementos de la **archivo** menú.

##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Inicializar sus propias aportaciones a estas clases

Las ilustraciones anteriores sugieren los puntos en el que puede invalidar las funciones miembro para inicializar los objetos de la aplicación. Una invalidación de `OnInitialUpdate` en la vista de clase es el mejor lugar para inicializar la vista. El `OnInitialUpdate` llamada se produce inmediatamente después de que se crea la ventana de marco y la vista dentro de la ventana de marco se adjunta a su documento. Por ejemplo, si la vista es una vista de desplazamiento (derivado de `CScrollView` lugar `CView`), debe establecer el tamaño de la vista según el tamaño del documento en su `OnInitialUpdate` invalidar. (Este proceso se describe en la descripción de la clase [CScrollView](../mfc/reference/cscrollview-class.md).) Puede invalidar el `CDocument` funciones miembro `OnNewDocument` y `OnOpenDocument` para proporcionar inicialización específica de la aplicación del documento. Normalmente, debe reemplazar ambos puesto que se puede crear un documento de dos maneras.

En la mayoría de los casos, la invalidación debe llamar a la versión de la clase base. Para obtener más información, vea las funciones miembro con nombre de las clases [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), y [CWinApp](../mfc/reference/cwinapp-class.md) en MFC Referencia de la biblioteca.

## <a name="see-also"></a>Vea también

[Las plantillas de documento y el proceso de creación de documento/vista](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Creación de plantillas de documentos](../mfc/document-template-creation.md)<br/>
[Crear documentos y vistas](../mfc/document-view-creation.md)<br/>
[Relaciones entre objetos MFC](../mfc/relationships-among-mfc-objects.md)

