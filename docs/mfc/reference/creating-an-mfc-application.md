---
title: Crear una aplicación MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec61db21b27ef49f660751605b4788599f7f3485
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062501"
---
# <a name="creating-an-mfc-application"></a>Crear una aplicación MFC

Una aplicación MFC es una aplicación ejecutable para Windows basada en la biblioteca Microsoft Foundation Class (MFC). La forma más fácil de crear una aplicación MFC es utilizar el Asistente para aplicaciones MFC.

> [!IMPORTANT]
>  Los proyectos MFC no se admiten en las ediciones Visual Studio Express.

Los archivos ejecutables MFC suelen ser de cinco tipos: las aplicaciones de Windows estándar, cuadros de diálogo, las aplicaciones basadas en formularios, aplicaciones estilo explorador y las aplicaciones estilo explorador Web. Para obtener más información, consulte:

- [Usar las clases para escribir aplicaciones de Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [Creación y visualización de cuadros de diálogo](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Creación de una aplicación MFC basada en formularios](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Creación de una aplicación MFC estilo Explorador de archivos](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Creación de una aplicación MFC estilo explorador web](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

El Asistente para aplicaciones MFC generará las clases y los archivos apropiados para estos tipos de aplicaciones, en función de las opciones que seleccione en el asistente.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>Para crear una aplicación MFC mediante el Asistente para aplicaciones MFC

1. Siga las instrucciones descritas en el tema de Ayuda [Crear un proyecto con el Asistente para aplicaciones de Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).

1. En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación MFC** en el panel Plantillas para abrir el asistente.

1. Defina la configuración de aplicación mediante el [MFC Application Wizard](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Omita este paso para mantener la configuración predeterminada del asistente.

1. Haga clic en **finalizar** para cerrar el asistente y abrir el proyecto nuevo en el entorno de desarrollo.

Una vez creado el proyecto, puede ver los archivos creados en **el Explorador de soluciones**. Para obtener más información sobre los archivos que crea el asistente para el proyecto, vea el archivo Readme.txt generado por el proyecto. Para obtener más información acerca de los tipos de archivo, consulte [tipos de archivo creados para proyectos de Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Vea también

[Agregar funcionalidad con los Asistentes para código](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Páginas de propiedades](../../ide/property-pages-visual-cpp.md)

