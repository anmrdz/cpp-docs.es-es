---
title: 'ODBC: Llamar a la API de ODBC directamente a las funciones | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 918ae8dd0249479cf8a99b1476e0beda5efc72f2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059810"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: Llamar directamente a funciones de la API de ODBC

Las clases de base de datos proporcionan una interfaz más sencilla para un [origen de datos](../../data/odbc/data-source-odbc.md) de ODBC. Como resultado, las clases no encapsulan toda la API de ODBC. Si hay alguna funcionalidad que se encuentre fuera de las capacidades de las clases, debe llamar a funciones API de ODBC directamente. Por ejemplo, deben llamar a las funciones de catálogo ODBC (`::SQLColumns`, `::SQLProcedures`, `::SQLTables`y otras) directamente.

> [!NOTE]
>  Mediante las clases ODBC de MFC, como se describe en este tema, o las clases DAO de MFC se puede tener acceso a los orígenes de datos ODBC.

Para llamar a una función de la API de ODBC directamente, debe realizar los mismos pasos que se tardaría si estuviera realizando las llamadas sin el marco de trabajo. Estos pasos son:

- Asignar almacenamiento para los resultados que devuelve la llamada.

- Pasar un ODBC `HDBC` o `HSTMT` controlar, dependiendo de la firma de parámetro de la función. Use la [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) macro para recuperar el identificador de ODBC.

   Variables de miembro `CDatabase::m_hdbc` y `CRecordset::m_hstmt` están disponibles para que no es necesario asignar e inicialice el usuario.

- Se puede llamar a funciones ODBC adicionales para preparar o realizar un seguimiento de la llamada principal.

- Cuando termine, desasignar almacenamiento.

Para obtener más información acerca de estos pasos, consulte el [Open Database Connectivity (ODBC)](/previous-versions/windows/desktop/ms710252) SDK en la documentación de MSDN.

Además de estos pasos, debe realizar pasos adicionales para comprobar los valores devueltos de función, asegúrese de que el programa no está esperando una llamada asincrónica al finalizar y así sucesivamente. Puede simplificar estos últimos pasos mediante el uso de las macros AFX_SQL_ASYNC y AFX_SQL_SYNC. Para obtener más información, consulte [Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md) en el *referencia de MFC*.

## <a name="see-also"></a>Vea también

[Conceptos básicos de ODBC](../../data/odbc/odbc-basics.md)
