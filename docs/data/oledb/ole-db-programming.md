---
title: Programación de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aafeb4aa4e723c4c3bea1398731b03492b37b1da
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071003"
---
# <a name="ole-db-programming"></a>Programación de OLE DB

OLE DB de Microsoft es una tecnología heredada; es la API de acceso de datos necesarios para los servidores vinculados de SQL para las aplicaciones nuevas. Todas las demás aplicaciones nuevas deben utilizar ODBC. El proveedor OLE DB actual para SQL Server es SQLNCLI11. ARCHIVO DLL. El proveedor aún se envía a SQL Server 2016. Esta documentación está dirigida a los desarrolladores que son mantener las aplicaciones existentes que ya usan OLE DB.

Las plantillas OLE DB son plantillas de C++ que facilitan el uso de la tecnología de base de datos de OLE DB de alto rendimiento, al proporcionar clases que implementan muchas interfaces OLE DB comúnmente usadas. Esta biblioteca de plantillas se divide en plantillas de consumidor y de proveedor.

Visual C++ también admite el asistente para la creación de aplicaciones de inicio de OLE DB.

Además, puede usar atributos para implementar las plantillas de consumidor OLE DB.

|Para obtener información adicional acerca de|Vea|
|-------------------------|---------|
|Utilizar las plantillas de consumidor OLE DB (temas conceptuales)|[Plantillas de consumidor OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)|
|Utilizar las plantillas de proveedor OLE DB (temas conceptuales)|[Plantillas de proveedores OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)|
|Clases y macros de plantillas OLE DB|[Referencia de plantillas OLE DB](../../data/oledb/ole-db-templates.md) (Visual C++)|
|Atributos de consumidor OLE DB|[Atributos de consumidor OLE DB](../../windows/ole-db-consumer-attributes.md)|
|Interfaces OLE DB|[Referencia del programador de OLE DB](/previous-versions/windows/desktop/ms713643(v%3dvs.85)) (en el SDK de Windows)|
|Ejemplos de plantillas OLE DB|[Ejemplos de plantillas OLE DB](https://github.com/Microsoft/VCSamples)|
|Información general sobre la programación de acceso a datos (Visual C++)|[Programación con Data Access](../../data/data-access-programming-mfc-atl.md)|
|Temas conceptuales de ODBC|[Conectividad abierta de bases de datos (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)|

## <a name="see-also"></a>Vea también

[Acceso a datos](../data-access-in-cpp.md)