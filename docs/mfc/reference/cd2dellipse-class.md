---
title: Clase CD2DEllipse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs:
- C++
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93fc2b788d450b591ebd20be49f25133c95f22b6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052861"
---
# <a name="cd2dellipse-class"></a>Clase CD2DEllipse

Contenedor para `D2D1_ELLIPSE`.

## <a name="syntax"></a>Sintaxis

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Sobrecargado. Construye un `CD2DEllipse` objeto `D2D1_ELLIPSE` objeto.|

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Requisitos

**Encabezado:** afxrendertarget.h

##  <a name="cd2dellipse"></a>  CD2DEllipse::CD2DEllipse

Construye un objeto CD2DEllipse del objeto CD2DRectF.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>Parámetros

*Rect*<br/>
rectángulo de origen

*elipse*<br/>
elipse de origen

*ptCenter*<br/>
El punto central de la elipse.

*sizeRadius*<br/>
El radio X y el radio Y de la elipse.

## <a name="see-also"></a>Vea también

[Clases](../../mfc/reference/mfc-classes.md)
