---
title: CMFCToolTipCtrl (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3a704f4c683e774057265604ecd69cd03dfb657
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056950"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl (clase)

Implementación extendida de información sobre herramientas basada en [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md). Una información sobre herramientas basada en la clase `CMFCToolTipCtrl` puede mostrar un icono, una etiqueta y una descripción. Puede personalizar su apariencia visual mediante un relleno de degradado, colores de texto y bordes personalizados, texto en negrita, esquinas redondeadas o un estilo de globo.

Para obtener más información, vea el código fuente ubicado en el **VC\\atlmfc\\src\\mfc** carpeta de la instalación de Visual Studio.

## <a name="syntax"></a>Sintaxis

```
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Constructor predeterminado.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Devuelve el tamaño de un icono en una información sobre herramientas.|
|[CMFCToolTipCtrl::GetParams](#getparams)|Devuelve la configuración de visualización en una información sobre herramientas.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Dibuja el borde de una información sobre herramientas.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Muestra un icono en una información sobre herramientas.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Dibuja la etiqueta de una información sobre herramientas o calcula el tamaño de la etiqueta.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Dibuja el separador entre la etiqueta y la descripción en una información sobre herramientas.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Rellena el fondo de la información sobre herramientas.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Establece la descripción que se mostrará en la información sobre herramientas.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|Especifica la apariencia visual de una información sobre herramientas con un objeto `CMFCToolTipInfo`.|

## <a name="remarks"></a>Comentarios

Use `CMFCToolTipCtrl`, `CMFCToolTipInfo`, y [CTooltipManager (clase)](../../mfc/reference/ctooltipmanager-class.md) objetos conjuntamente para implementar información sobre herramientas personalizada en su aplicación.

Por ejemplo, para usar informaciones sobre herramientas con estilo de globo, siga estos pasos:

1. Use la [CWinAppEx (clase)](../../mfc/reference/cwinappex-class.md) método para inicializar el Administrador de información sobre herramientas en la aplicación.

2. Cree una estructura `CMFCToolTipInfo` para especificar el estilo visual que desee:

```
CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
{
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

}
```
3. Use la [ctooltipmanager:: Settooltipparams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) método para establecer el estilo visual de todas las informaciones sobre herramientas en la aplicación mediante el uso de los estilos definidos en el `CMFCToolTipInfo` objeto:

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```
También puede derivar una clase nueva de `CMFCToolTipCtrl` para controlar la representación y el comportamiento de la información sobre herramientas. Para especificar una nueva clase de control de información sobre herramientas, use el método `CTooltipManager::SetTooltipParams`:

```
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```
Para restaurar la clase de control predeterminada de información sobre herramientas y restablecer la apariencia de esta información a su estado predeterminado, especifique NULL en los parámetros de información sobre herramientas y de información de clase en tiempo de ejecución de `SetTooltipParams`:

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo construir un objeto `CMFCToolTipCtrl`, se establece la descripción que se muestra en la información sobre herramientas y se establece también el ancho del control de esta información.

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>Requisitos

**Encabezado:** afxtooltipctrl.h

##  <a name="cmfctooltipctrl"></a>  CMFCToolTipCtrl::CMFCToolTipCtrl

```
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>Parámetros

[in] *pParams*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="geticonsize"></a>  CMFCToolTipCtrl::GetIconSize

Devuelve el tamaño de un icono en una información sobre herramientas.

```
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Valor devuelto

El tamaño del icono, en píxeles.

##  <a name="getparams"></a>  CMFCToolTipCtrl::GetParams

Devuelve la configuración de visualización en una información sobre herramientas.

```
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Valor devuelto

La configuración de pantalla de información sobre herramientas actual, que se almacena en un [CMFCToolTipInfo (clase)](../../mfc/reference/cmfctooltipinfo-class.md) objeto.

##  <a name="ondrawborder"></a>  CMFCToolTipCtrl::OnDrawBorder

Dibuja el borde de una información sobre herramientas.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parámetros

*pDC*<br/>
[in] Puntero a un contexto de dispositivo.

*Rect*<br/>
[in] El rectángulo delimitador de la información sobre herramientas.

*clrLine*<br/>
[in] Color del borde.

### <a name="remarks"></a>Comentarios

Invalide este método en una clase derivada para personalizar la apariencia del borde de información sobre herramientas.

##  <a name="ondrawdescription"></a>  CMFCToolTipCtrl::OnDrawDescription

```
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parámetros

[in] *pDC*<br/>
[in] *rect*<br/>
[in] *bCalcOnly*<br/>

### <a name="return-value"></a>Valor devuelto

### <a name="remarks"></a>Comentarios

##  <a name="ondrawicon"></a>  CMFCToolTipCtrl::OnDrawIcon

Muestra un icono en una información sobre herramientas.

```
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>Parámetros

*pDC*<br/>
[in] Un puntero a un contexto de dispositivo.

*rectImage*<br/>
[in] Coordenadas del icono.

### <a name="return-value"></a>Valor devuelto

TRUE si se ha dibujado el icono. En caso contrario, FALSE.

### <a name="remarks"></a>Comentarios

Invalide este método en una clase derivada para mostrar un icono personalizado. También debe invalidar [CMFCToolTipCtrl::GetIconSize](#geticonsize) para habilitar la información sobre herramientas calcular correctamente el diseño de texto y la descripción.

##  <a name="ondrawlabel"></a>  CMFCToolTipCtrl::OnDrawLabel

Dibuja la etiqueta de una información sobre herramientas o calcula el tamaño de la etiqueta.

```
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parámetros

*pDC*<br/>
[in] Un puntero a un contexto de dispositivo.

*Rect*<br/>
[in] Rectángulo delimitador del área de etiqueta.

*bCalcOnly*<br/>
[in] Si es TRUE, no se dibujará la etiqueta.

### <a name="return-value"></a>Valor devuelto

Tamaño de la etiqueta, en píxeles.

### <a name="remarks"></a>Comentarios

Invalide este método en una clase derivada si desea personalizar la apariencia de la etiqueta de información sobre herramientas.

##  <a name="ondrawseparator"></a>  CMFCToolTipCtrl::OnDrawSeparator

Dibuja el separador entre la etiqueta y la descripción en una información sobre herramientas.

```
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>Parámetros

*pDC*<br/>
[in] Un puntero a un contexto de dispositivo.

*X1*<br/>
[in] Coordenada horizontal del extremo izquierdo del separador.

*X2*<br/>
[in] Coordenada horizontal del extremo derecho del separador.

*Y*<br/>
[in] Coordenada vertical del separador.

### <a name="remarks"></a>Comentarios

La implementación predeterminada dibuja una línea desde el punto (x1, y) para el punto (x2, y).

Invalide este método en una clase derivada para personalizar la apariencia del separador.

##  <a name="onfillbackground"></a>  CMFCToolTipCtrl::OnFillBackground

Rellena el fondo de la información sobre herramientas.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>Parámetros

*pDC*<br/>
[in] Un puntero a un contexto de dispositivo.

*Rect*<br/>
[in] Especifica el rectángulo delimitador del área de relleno.

*clrText*<br/>
[in] Color de primer plano de la información sobre herramientas.

*clrLine*<br/>
[in] Color de los bordes y la línea de delimitador entre etiqueta y una descripción.

### <a name="remarks"></a>Comentarios

La implementación predeterminada rellena el rectángulo especificado por *rect* con el color o el patrón especificado por la llamada más reciente a [CMFCToolTipCtrl::SetParams](#setparams).

Invalide este método en una clase derivada si desea personalizar la apariencia de la información sobre herramientas.

##  <a name="setdescription"></a>  CMFCToolTipCtrl::SetDescription

Establece la descripción que se mostrará en la información sobre herramientas.

```
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>Parámetros

*strDesrciption*<br/>
[in] Texto de descripción.

### <a name="remarks"></a>Comentarios

El texto de descripción se muestra en la información sobre herramientas en el separador.

##  <a name="setfixedwidth"></a>  CMFCToolTipCtrl::SetFixedWidth

```
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>Parámetros

[in] *nWidthRegular*<br/>
[in] *nWidthLargeImage*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="sethotribbonbutton"></a>  CMFCToolTipCtrl::SetHotRibbonButton

```
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>Parámetros

[in] *pRibbonButton*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="setlocation"></a>  CMFCToolTipCtrl::SetLocation

```
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>Parámetros

[in] *pt*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="setparams"></a>  CMFCToolTipCtrl::SetParams

Especifica la apariencia visual de una información sobre herramientas con un [CMFCToolTipInfo (clase)](../../mfc/reference/cmfctooltipinfo-class.md) objeto.

```
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>Parámetros

*pParams*<br/>
[in] Puntero a un [CMFCToolTipInfo (clase)](../../mfc/reference/cmfctooltipinfo-class.md) objeto que contiene los parámetros de visualización.

### <a name="remarks"></a>Comentarios

Cada vez que se muestra la información sobre herramientas, que se dibuja mediante el uso de los colores y los estilos visuales que *pParams* especifica. El valor de *pParams* se almacena en el miembro protegido `m_Params`, que se puede acceder mediante una clase derivada que reemplaza [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl: : OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), o [CMFCToolTipCtrl::OnFillBackground](#onfillbackground)para mantener el aspecto especificado.

## <a name="see-also"></a>Vea también

[Gráfico de jerarquías](../../mfc/hierarchy-chart.md)<br/>
[Clases](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl (clase)](../../mfc/reference/ctooltipctrl-class.md)<br/>
[CTooltipManager (clase)](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipInfo (clase)](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx (clase)](../../mfc/reference/cwinappex-class.md)
