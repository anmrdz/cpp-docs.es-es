---
title: Uso de un conjunto de registros ADO existente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1433b51a6dfe6f558b98360812e694d42ebfb9f5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50051958"
---
# <a name="using-an-existing-ado-recordset"></a>Utilizar un conjunto de registros ADO existente

Para mezclar las plantillas de consumidor OLE DB y Active Data Objects (ADO), utilice ADO para abrir un conjunto de registros (correspondiente a un conjunto de filas en las plantillas de consumidor OLE DB). Cuando haya un conjunto de registros, haga lo siguiente para conectarse a un conjunto de filas de OLE DB:

1. Llame a `QueryInterface` para el `IRowset` y `IAccessor` punteros.

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* apunta a la `IUnknown` objeto del conjunto de registros ADO.

1. Asociar el descriptor de acceso y el conjunto de filas a sus clases de plantillas de consumidor OLE DB apropiados.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>Vea también

[Usar descriptores de acceso](../../data/oledb/using-accessors.md)