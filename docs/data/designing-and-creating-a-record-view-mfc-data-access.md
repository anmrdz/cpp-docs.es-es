---
title: Diseñar y crear una vista de registros (acceso a datos MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- designing forms
- record views, creating
- forms [C++], designing
- record views, designing
- application wizards [C++], creating record view classes
- designing record views
ms.assetid: 1d6f5439-754f-4b8b-a19d-841a4657827b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c03b85538a795142f5085c93df3a60f4c60481ab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065855"
---
# <a name="designing-and-creating-a-record-view--mfc-data-access"></a>Diseñar y crear una vista de registros (acceso a datos MFC)

Puede crear la clase de vista de registros con el [MFC Application Wizard](../mfc/reference/database-support-mfc-application-wizard.md). Si utiliza un asistente para aplicaciones, este crea la clase de vista de registros y un recurso de plantilla de cuadro de diálogo (sin controles). Debe utilizar el editor de cuadros de diálogo de Visual C++ para agregar controles al recurso de plantilla de cuadro de diálogo. Por otro lado, si usa **Agregar clase**, debe crear primero el recurso de plantilla de cuadro de diálogo en el cuadro de diálogo editor y, a continuación, crear la clase de vista de registros.

#### <a name="to-create-your-record-view-with-the-mfc-application-wizard"></a>Cómo crear la vista de registros con el asistente para aplicaciones MFC

1. Consulte [base de datos, Asistente para aplicaciones MFC](../mfc/reference/database-support-mfc-application-wizard.md).

#### <a name="to-design-your-form"></a>Cómo diseñar el formulario

1. Consulte [Editor de cuadro de diálogo](../windows/dialog-editor.md).

#### <a name="to-create-your-record-view-class"></a>Cómo crear la clase de vista de registros

1. Consulte [agregar un consumidor ODBC MFC](../mfc/reference/adding-an-mfc-odbc-consumer.md).

Los siguientes temas explican más detalles sobre el uso de vistas de registros:

- [Vistas de registros: Permitir la navegación en una vista de registros](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)

- [Vistas de registros: Utilizar una vista de registros](../data/using-a-record-view-mfc-data-access.md)

- [Vistas de registros: Llenar un cuadro de lista de otro conjunto de registros](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)

## <a name="see-also"></a>Vea también

[Vistas de registros (acceso a datos MFC)](../data/record-views-mfc-data-access.md)<br/>
[Conjunto de registros (ODBC)](../data/odbc/recordset-odbc.md)<br/>
[Lista de controladores ODBC](../data/odbc/odbc-driver-list.md)