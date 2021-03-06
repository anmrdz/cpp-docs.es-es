---
title: Derivar una clase de documento de CDocument | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b45dadbc062bbba61cdcb4c883f91943b1b18ba8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429830"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Derivar una clase de documento de CDocument

Documentos contienen y administran datos de la aplicación. Para usar la clase de documento proporcionado por el Asistente para aplicaciones MFC, debe hacer lo siguiente:

- Derive una clase de `CDocument` para cada tipo de documento.

- Agregar variables miembro para almacenar los datos de cada documento.

- Invalidar `CDocument`del `Serialize` función miembro en la clase de documento. `Serialize` escribe y lee los datos del documento hacia y desde el disco.

## <a name="other-document-functions-often-overridden"></a>Otras funciones de documento que se reemplazan con frecuencia

También puede invalidar otros `CDocument` funciones miembro. En concreto, a menudo será necesario invalidar [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) y [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) para inicializar los miembros de datos del documento y [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) destruir asigna dinámicamente los datos. Para obtener información acerca de los miembros reemplazables, vea la clase [CDocument](../mfc/reference/cdocument-class.md) en el *referencia de MFC*.

## <a name="see-also"></a>Vea también

[Uso de documentos](../mfc/using-documents.md)

