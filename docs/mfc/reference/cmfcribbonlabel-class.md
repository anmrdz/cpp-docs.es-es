---
title: CMFCRibbonLabel (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d54662663e2b3223f4122eae93327b9a05337b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382237"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel (clase)

Implementa una etiqueta de texto no seleccionable en una cinta.

## <a name="syntax"></a>Sintaxis

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Crea e inicializa un `CMFCRibbonLabel` objeto con la cadena de texto especificado.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Destructor.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Usado por el marco para crear una instancia dinámica de este tipo de clase.|
|`CMFCRibbonLabel::GetThisClass`|Usa el marco de trabajo para obtener un puntero a la [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objeto que está asociado con este tipo de clase.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Determina los datos de accesibilidad para el elemento actual de etiqueta de cinta de opciones. (Invalida [cmfcribbonbutton:: Setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>Comentarios

Después de crear una etiqueta de cinta de opciones, agréguelo a un panel mediante una llamada a [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

No se puede agregar una etiqueta de cinta de opciones en la barra de herramientas de acceso rápido.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Requisitos

**Encabezado:** afxRibbonLabel.h

##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel

Crea e inicializa un [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) objeto que muestra la cadena de texto especificado.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Parámetros

*lpszText*<br/>
[in] Texto que aparecerá en la etiqueta.

*bIsMultiLine*<br/>
[in] TRUE para especificar que la etiqueta es una etiqueta de varias líneas; en caso contrario, FALSE.

##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData

Determina los datos de accesibilidad para el elemento actual de etiqueta de cinta de opciones.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parámetros

*pParent*<br/>
[in] Representa la ventana primaria de la etiqueta actual de la cinta de opciones.

*data*<br/>
[out] Un objeto de tipo `CAccessibilityData` que se rellena con los datos de accesibilidad de la etiqueta actual de la cinta de opciones.

### <a name="return-value"></a>Valor devuelto

TRUE si el *datos* parámetro era correctamente rellenada con los datos de accesibilidad de la etiqueta de cinta actual; en caso contrario, FALSE.

## <a name="see-also"></a>Vea también

[Gráfico de jerarquías](../../mfc/hierarchy-chart.md)<br/>
[Clases](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton (clase)](../../mfc/reference/cmfcribbonbutton-class.md)
