---
title: MEASUREITEMSTRUCT (estructura) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MEASUREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db24d772e2f007b3350443ae6bc84f97cac34e76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397772"
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT (Estructura)

El `MEASUREITEMSTRUCT` estructura informa a Windows de las dimensiones de un elemento de menú o control dibujado por el propietario.

## <a name="syntax"></a>Sintaxis

```
typedef struct tagMEASUREITEMSTRUCT {
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    UINT itemWidth;
    UINT itemHeight;
    DWORD itemData
} MEASUREITEMSTRUCT;
```

#### <a name="parameters"></a>Parámetros

*CtlType*<br/>
Contiene el tipo de control. Los valores de tipos de control son los siguientes:

- Cuadro combinado ODT_COMBOBOX dibujado por el propietario

- Cuadro de lista dibujado por el propietario odt_combobox

- Menú dibujado por el propietario ODT_MENU

*CtlID*<br/>
Contiene el identificador del control de un cuadro combinado, un cuadro de lista o un botón. Este miembro no se usa para un menú.

*itemID*<br/>
Contiene el identificador del elemento de menú para un menú o el identificador de elemento de cuadro de lista de un cuadro combinado de alto variable o un cuadro de lista. Este miembro no se utiliza para un cuadro combinado de alto fijo o un cuadro de lista, o para un botón.

*itemWidth*<br/>
Especifica el ancho de un elemento de menú. El propietario del elemento de menú dibujado por el propietario debe rellenar a este miembro antes de devolver desde el mensaje.

*itemHeight*<br/>
Especifica el alto de un elemento individual en un cuadro de lista o un menú. Antes de devolver desde el mensaje, el propietario del cuadro combinado dibujado por el propietario, cuadro de lista o elemento de menú debe rellenar este miembro. El alto máximo de un elemento de cuadro de lista es de 255.

*itemData*<br/>
Para un cuadro combinado o cuadro de lista, este miembro contiene el valor que uno de los siguientes elementos pasó al cuadro de lista:

- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)

- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)

- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)

- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)

Para un menú, este miembro contiene el valor que uno de los siguientes elementos pasó al cuadro de lista:

- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)

- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)

- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)

Esto permite que Windows a la interacción del usuario con el control se procesen correctamente. Error al rellenar los miembros adecuados en el `MEASUREITEMSTRUCT` estructura provocará un funcionamiento incorrecto del control.

## <a name="requirements"></a>Requisitos

**Encabezado:** winuser.h

## <a name="see-also"></a>Vea también

[Estructuras, estilos, devoluciones de llamada y mapas de mensajes](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

