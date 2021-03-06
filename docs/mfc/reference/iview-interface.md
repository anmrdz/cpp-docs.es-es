---
title: Interfaz IView | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84ed9bfb8b0c8b5ab30af07d8f0448109161df51
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077769"
---
# <a name="iview-interface"></a>Interfaz IView

Implementa varios métodos que [CWinFormsView](../../mfc/reference/cwinformsview-class.md) usa para enviar notificaciones de la vista a un control administrado.

## <a name="syntax"></a>Sintaxis

```
interface class IView
```

## <a name="members"></a>Miembros

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Se llama por MFC cuando se activa o desactiva una vista.|
|[IView:: OnInitialUpdate](#oninitialupdate)|Lo llama el marco de trabajo después de la vista se adjunta al documento en primer lugar, pero antes de la vista se muestra inicialmente.|
|[IView::OnUpdate](#onupdate)|Se llama por MFC después de que se ha modificado el documento de la vista; Esta función permite que la vista que actualice su presentación para reflejar las modificaciones.|

## <a name="remarks"></a>Comentarios

`IView` implementa varios métodos que `CWinFormsView` usa para enviar notificaciones de vista comunes para un control administrado hospedado. Estos son [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) y [OnActivateView](#onactivateview).

`IView` es similar a [CView](../../mfc/reference/cview-class.md), pero solo se usa con las vistas administradas y los controles.

Para obtener más información sobre el uso de Windows Forms, consulte [mediante un Control de usuario de Windows Forms en MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Requisitos

Encabezado: afxwinforms.h (definido en el ensamblado atlmfc\lib\mfcmifc80.dll)

## <a name="onactivateview"></a> IView::OnActivateView

Se llama por MFC cuando se activa o desactiva una vista.
```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Parámetros

*Activar*<br/>
Indica si la vista se está activando o desactivando.

## <a name="oninitialupdate"></a> IView:: OnInitialUpdate

Lo llama el marco de trabajo después de la vista se adjunta al documento en primer lugar, pero antes de la vista se muestra inicialmente.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate

Llamado por MFC cuando se ha modificado el documento de la vista.
```
void OnUpdate();
```

## <a name="remarks"></a>Comentarios

Esta función permite que la vista que actualice su presentación para reflejar las modificaciones.

## <a name="see-also"></a>Vea también

[CWinFormsView (clase)](../../mfc/reference/cwinformsview-class.md)<br/>
[CView (clase)](../../mfc/reference/cview-class.md)
