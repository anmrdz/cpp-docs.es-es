---
title: DELETEITEMSTRUCT (estructura) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9061205bdf3697e492b846d160a5b4dd2d154bb9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065023"
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT (Estructura)

El `DELETEITEMSTRUCT` estructura describe un elemento eliminado de cuadro de lista o cuadro combinado dibujado por el propietario.

## <a name="syntax"></a>Sintaxis

```
typedef struct tagDELETEITEMSTRUCT { /* ditms */
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    HWND hwndItem;
    UINT itemData;
} DELETEITEMSTRUCT;
```

#### <a name="parameters"></a>Parámetros

*CtlType*<br/>
Especifica odt_combobox (un cuadro de lista dibujado por el usuario) o ODT_COMBOBOX (un cuadro combinado dibujado por el propietario).

*CtlID*<br/>
Especifica el identificador del cuadro de lista o cuadro combinado.

*itemID*<br/>
Especifica el índice del elemento en el cuadro de lista o cuadro combinado que se va a quitar.

*hwndItem*<br/>
Identifica el control.

*itemData*<br/>
Especifica los datos definidos por la aplicación para el elemento. Este valor se pasa al control en el *lParam* parámetro del mensaje que se agrega el elemento al cuadro de lista o cuadro combinado.

## <a name="remarks"></a>Comentarios

Cuando se quita un elemento desde el cuadro de lista o cuadro combinado o cuando se destruye el cuadro de lista o cuadro combinado, Windows envía el mensaje WM_DELETEITEM al propietario para cada elemento eliminado. El *lParam* parámetro del mensaje contiene un puntero a esta estructura.

## <a name="requirements"></a>Requisitos

**Encabezado:** atldbcli.h

## <a name="see-also"></a>Vea también

[Estructuras, estilos, devoluciones de llamada y mapas de mensajes](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)

