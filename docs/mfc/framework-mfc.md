---
title: Marco (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87db7b28ec340a76c074a7b32c0e182030042eeb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381964"
---
# <a name="framework-mfc"></a>Marco (MFC)

El trabajo con el marco de trabajo de la biblioteca Microsoft Foundation Class (MFC) se basa en gran medida en algunas clases principales y varias herramientas de Visual C++. Algunas clases encapsulan una gran parte de la interfaz de programación de aplicaciones (API) Win32. Otras clases encapsulan los conceptos de las aplicaciones, como documentos, vistas y la propia aplicación. Algunas clases encapsulan funciones OLE y la funcionalidad de acceso a datos ODBC y DAO.

Por ejemplo, se encapsula el concepto de Win32 de ventana mediante la clase MFC `CWnd`. Es decir, una clase de C++ denomina `CWnd` encapsula o "ajusta" los `HWND` identificador que representa una ventana de Windows. Del mismo modo, la clase `CDialog` encapsula los cuadros de diálogo de Win32.

Encapsulación significa que la clase de C++ `CWnd`, por ejemplo, contiene una variable de miembro de tipo `HWND`, y las funciones miembro de la clase encapsulan las llamadas a funciones de Win32 que toman un `HWND` como un parámetro. Las funciones miembro de clase suelen tengan el mismo nombre que la función de Win32 que encapsulan.

## <a name="in-this-section"></a>En esta sección

[SDI y MDI](../mfc/sdi-and-mdi.md)

[Documentos, vistas y el marco](../mfc/documents-views-and-the-framework.md)

[Asistentes y editores de recursos](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>En secciones relacionadas

[Compilación en el marco](../mfc/building-on-the-framework.md)

[Cómo el marco llama al código](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: la clase Application](../mfc/cwinapp-the-application-class.md)

[Las plantillas de documento y el proceso de creación de documento/vista](../mfc/document-templates-and-the-document-view-creation-process.md)

[Control y asignación de mensajes](../mfc/message-handling-and-mapping.md)

[Objetos de ventana](../mfc/window-objects.md)

## <a name="see-also"></a>Vea también

[Uso de las clases para escribir aplicaciones para Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
