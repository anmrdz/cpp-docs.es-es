---
title: Clases de base de datos ATL (plantillas OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b5147610e580d3a67400893d41af8ad9728cc72a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071224"
---
# <a name="atl-database-classes-ole-db-templates"></a>Clases de base de datos ATL (plantillas OLE DB)

Microsoft proporciona varias implementaciones de OLE DB, un conjunto de interfaces COM que proporcionan acceso uniforme a datos de diversos orígenes de información y formatos.  OLE DB esté oficialmente en desuso; Esta documentación es para los desarrolladores que están realizando el mantenimiento código heredado. Aplicaciones nuevas deben utilizar ODBC para conectarse a orígenes de datos SQL.

Las plantillas OLE DB son plantillas de C++ en ATL que facilitan la tecnología de base de datos de OLE DB usar al proporcionar clases que implementan muchas de las interfaces OLE DB más utilizadas.

Esta biblioteca de plantillas contiene dos partes:

- [Plantillas de consumidor OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) usado para implementar una aplicación de cliente (consumidor) de OLE DB.

- [Plantillas de proveedores OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) usado para implementar una aplicación de servidor (proveedor) de OLE DB.

Además, el [atributos de consumidor OLE DB](../windows/ole-db-consumer-attributes.md) proporcionan una manera cómoda para crear consumidores OLE DB. Los atributos OLE DB insertan código basado en las plantillas de consumidor OLE DB para crear consumidores OLE DB de trabajo.

Observe que la biblioteca MFC contiene una clase, [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), que muestra los registros de base de datos en controles. La vista es una vista de formulario conectada directamente a un `CRowset` de objetos y muestra los campos de la `CRowset` objeto en los controles de la plantilla de cuadro de diálogo.

Para obtener más información, consulte [programación de OLE DB](../data/oledb/ole-db-programming.md) y [Guía del programador de OLE DB](/previous-versions/windows/desktop/ms713643).

## <a name="see-also"></a>Vea también

[Crear un consumidor OLE DB](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[Crear un proveedor OLE DB](../data/oledb/creating-an-ole-db-provider.md)<br/>
[Referencia de plantillas de consumidor OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Referencia de plantillas de proveedores OLE DB](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Ejemplos de plantillas OLE DB](https://github.com/Microsoft/VCSamples)