---
title: CMFCToolBarComboBoxEdit (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01d04960adf8de43c72972e5c46d6f549003c6e7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378961"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit (clase)

El marco de trabajo usa el `CMFCToolBarComboBoxEdit` clase para crear un botón de barra de herramientas que se comporta como un control de cuadro combinado editable.

## <a name="syntax"></a>Sintaxis

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](#cmfctoolbarcomboboxedit)|Construye un objeto `CMFCToolBarComboBoxEdit`.|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|Destructor.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|Traduce los mensajes de ventana antes de enviarlos a la [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) y [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) funciones de Windows. (Invalida [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)).|

### <a name="remarks"></a>Comentarios

Derive una clase de la `CMFCToolBarComboBoxEdit` clase para personalizar sus operaciones de edición.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>Requisitos

**Encabezado:** afxtoolbarcomboboxbutton.h

##  <a name="cmfctoolbarcomboboxedit"></a>  CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit

Construye un objeto `CMFCToolBarComboBoxEdit`.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>Parámetros

*Cuadro combinado*<br/>
[in] Una referencia a un [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) objeto, que es un botón de barra de herramientas que contiene un control de cuadro combinado.

### <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo construir un objeto de la `CMFCToolBarComboBoxEdit` clase. Este fragmento de código forma parte de la [ejemplo de demostración de IE](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>Vea también

[Gráfico de jerarquías](../../mfc/hierarchy-chart.md)<br/>
[Clases](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton (clase)](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
