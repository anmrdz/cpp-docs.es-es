---
title: Subprocesos y clases ODBC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab115db1387adb71a69b735d676fa657d370752f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052478"
---
# <a name="odbc-classes-and-threads"></a>Clases y subprocesos de ODBC

A partir de MFC 4.2, no hay compatibilidad con multithreading para las clases ODBC de MFC. Sin embargo, tenga en cuenta que MFC no proporciona compatibilidad con multithreading para las clases DAO.

La compatibilidad con multithreading para las clases ODBC tiene algunas limitaciones. Dado que estas clases ajustan a la API de ODBC, están limitadas a la compatibilidad con multithreading de los componentes en el que se crearon. Por ejemplo, muchos controladores ODBC no son seguros para subprocesos; por lo tanto, las clases ODBC de MFC no son subprocesos si usas con uno de estos controladores. Debe comprobar si su controlador determinado es segura para subprocesos.

Al crear una aplicación multiproceso, debe ser muy cuidadoso en uso de varios subprocesos para manipular el mismo objeto. Por ejemplo, con el mismo `CRecordset` objeto en los dos subprocesos puede causar problemas al recuperar los datos; una operación de captura en un subproceso podría sobrescribir los datos capturados en el otro subproceso. Un uso más común de las clases ODBC de MFC en subprocesos independientes es compartir una apertura `CDatabase` objeto entre varios subprocesos para usar la misma conexión de ODBC, con otro `CRecordset` objeto en cada subproceso. Tenga en cuenta que no se debe pasar una sin abrir `CDatabase` objeto a un `CRecordset` objeto en otro subproceso.

> [!NOTE]
>  Si debe tener varios subprocesos y manipular el mismo objeto, debe implementar los mecanismos de sincronización apropiado, como secciones críticas. Tenga en cuenta que ciertas operaciones, tales como `Open`, no están protegidos. Debe asegurarse de que estas operaciones no se llamará al mismo tiempo en subprocesos independientes.

Para obtener más información sobre cómo crear aplicaciones multiproceso, consulte [temas de Multithreading](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

## <a name="see-also"></a>Vea también

[Conectividad abierta de bases de datos (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Acceso a los datos de programación (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)