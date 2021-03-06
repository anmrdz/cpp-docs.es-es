---
title: Migración de aplicaciones de datos | Microsoft Docs
ms.custom: ''
ms.date: 05/12/2017
ms.technology:
- devlang-cpp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 8d10c285-c13f-4e6e-a09e-5ee0f2666b44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51b041c60cd1bb8f866a6174e3cbb41ad613acc0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078172"
---
# <a name="porting-data-applications"></a>Migración de aplicaciones de datos
Con los años, Visual C++ ha ido proporcionando varias maneras de trabajar con bases de datos. En 2011, Microsoft anunció que se adhería a ODBC, la tecnología recomendada para tener acceso a los productos de SQL Server desde código nativo. ODBC es un estándar del sector, de modo que, al usarlo, obtendrá la mejor portabilidad de código posible en varias plataformas y orígenes de datos. La mayoría de los productos de base de datos SQL y muchos productos que no son de SQL son compatibles con ODBC. Puede usar ODBC directamente mediante una llamada a las API de ODBC de bajo nivel, o bien usar las clases contenedoras de ODBC MFC o una biblioteca de contenedor de C++ de terceros.

OLE DB es una API de bajo nivel y de alto rendimiento basada en la especificación COM que solo se admite en Windows. Use OLE DB si el programa tiene acceso a [servidores vinculados](/sql/relational-databases/linked-servers/linked-servers-database-engine). ATL proporciona plantillas de OLE DB que hacen que sea más fácil crear consumidores y proveedores OLE DB personalizados. La versión más reciente de OLE DB se suministra con SQL Native Client 11.

Si la aplicación heredada usa OLE DB o la interfaz de nivel superior de ADO para conectarse a SQL Server y no está teniendo acceso a servidores vinculados, considere la posibilidad de migrar a ODBC en un futuro próximo. Si no necesita portabilidad entre plataformas o las características de SQL Server más recientes, posiblemente pueda usar el Proveedor OLE DB de Microsoft para ODBC (MSDASQL).  MSDASQL permite que las aplicaciones basadas en OLE DB y ADO (que usa OLEDB internamente) tengan acceso a los orígenes de datos a través de un controlador ODBC. Al igual que cualquier capa de traducción, MSDASQL puede tener impacto en el rendimiento de la base de datos. Conviene hacer pruebas para saber si el impacto va a ser significativo en la aplicación. MSDASQL se suministra con el sistema operativo Windows, y Windows Server 2008 y Windows Vista SP1 son las primeras versiones de Windows que incluyeron una versión de 64 bits de esta tecnología.

El componente SQL Native Client (SNAC), que empaqueta los controladores ODBC y OLE DB en un solo archivo DLL, está en desuso para las aplicaciones de ODBC. La versión de SQL Server 2012 de SNAC (SQLNCLI11.DLL) se incluye con SQL Server 2016 porque otros componentes de SQL Server que dependen de ella. Pese a ello, las nuevas aplicaciones de C++ que se conecten a SQL Server o a Azure SQL Database mediante ODBC deben usar [el controlador ODBC más reciente](/sql/connect/odbc/download-odbc-driver-for-sql-server). Para más información, vea [SQL Server Native Client Programming](/sql/relational-databases/native-client/sql-server-native-client-programming) (Programación de SQL Server Native Client).

Si usa C++/CLI, puede seguir usando ADO.NET como siempre. Para más información, vea [Acceso a datos mediante ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) y [Obtener acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

- Aparte de las clases de contenedor ODBC, MFC también proporciona clases de contenedor DAO (objetos de acceso a datos) para conectarse a las bases de datos de Access.  Sin embargo, DAO está obsoleto. Cualquier código basado en `CDaoDatabase` o `CDaoRecordset` debe actualizarse.

Para más información sobre la historia de las tecnologías de acceso a datos en Microsoft Windows, vea el artículo de la Wikipedia sobre [Componentes de Microsoft Data Access](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>Vea también

[Acceso a datos en Visual C++](../data/data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
[Mapa de ruta de tecnologías de acceso a datos](https://msdn.microsoft.com/library/ms810810.aspx)