---
title: Insertar un formulario en un proyecto | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba22c87ee601d66ccfb1092047e69be42d8163c3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052763"
---
# <a name="inserting-a-form-into-a-project"></a>Insertar un formulario en un proyecto

Formularios proporcionan un práctico contenedor para los controles. Puede insertar fácilmente un formulario basado en MFC en la aplicación siempre que la aplicación es compatible con las bibliotecas MFC.

### <a name="to-insert-a-form-into-your-project"></a>Para insertar un formulario en el proyecto

1. Desde la vista de clases, seleccione el proyecto al que desea agregar el formulario y haga clic en el botón secundario del mouse.

1. En el menú contextual, haga clic en **agregar** y, a continuación, haga clic en **Agregar clase**.

   Si el **nuevo formulario** comando no está disponible, el proyecto se puede basar en Active Template Library (ATL). Para agregar un formulario a un proyecto ATL, primero debe [especificar determinados valores](../atl/reference/application-settings-atl-project-wizard.md) cuando empiece a crear el proyecto.

1. Desde el **MFC** carpeta, haga clic en **clase MFC**.

1. Utilizando el Asistente para clases MFC, asegúrese de derivar de la nueva clase [CFormView](../mfc/reference/cformview-class.md).

Visual C++ agrega el formulario a la aplicación, ábralo en el editor de cuadro de diálogo para que puede empezar a agregar controles y trabajar en su diseño global.

Es posible que desee realizar los siguientes pasos adicionales (no aplicables para las aplicaciones basadas en el cuadro de diálogo):

1. Invalidar el `OnUpdate` función miembro.

1. Implemente una función miembro para mover datos desde la vista al documento.

1. Crear un `OnPrint` función miembro.

## <a name="see-also"></a>Vea también

[Vistas de formulario](../mfc/form-views-mfc.md)

