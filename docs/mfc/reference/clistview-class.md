---
title: CListView (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
dev_langs:
- C++
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fbb9561111a75011f934aeb0ce972829132cb87
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423408"
---
# <a name="clistview-class"></a>CListView (clase)

Simplifica el uso del control de lista y de [CListCtrl](../../mfc/reference/clistctrl-class.md), la clase que encapsula la funcionalidad de control de lista, con la arquitectura de vista-documento de MFC.

## <a name="syntax"></a>Sintaxis

```
class CListView : public CCtrlView
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CListView::CListView](#clistview)|Construye un objeto `CListView`.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CListView::GetListCtrl](#getlistctrl)|Devuelve el control de lista asociado a la vista.|

### <a name="protected-methods"></a>Métodos protegidos

|Name|Descripción|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|Quita la lista de imágenes especificado de la vista de lista.|

## <a name="remarks"></a>Comentarios

Para obtener más información acerca de esta arquitectura, consulte la información general de la [CView](../../mfc/reference/cview-class.md) clase y las referencias cruzadas citadas no existe.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Requisitos

**Encabezado:** afxcview.h

##  <a name="clistview"></a>  CListView::CListView

Construye un objeto `CListView`.

```
CListView();
```

##  <a name="getlistctrl"></a>  CListView::GetListCtrl

Llame a esta función miembro para obtener una referencia al control de lista asociado a la vista.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Valor devuelto

Una referencia al control de lista asociado a la vista.

### <a name="example"></a>Ejemplo

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

##  <a name="removeimagelist"></a>  CListView::RemoveImageList

Quita la lista de imágenes especificado de la vista de lista.

```
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Parámetros

*nImageList*<br/>
Índice de base cero de la imagen para quitar.

## <a name="see-also"></a>Vea también

[Ejemplo de MFC ROWLIST](../../visual-cpp-samples.md)<br/>
[CCtrlView (clase)](../../mfc/reference/cctrlview-class.md)<br/>
[Gráfico de jerarquías](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView (clase)](../../mfc/reference/cctrlview-class.md)
