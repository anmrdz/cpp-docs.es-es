---
title: CMenuTearOffManager (clase) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9d33f5cb060bfab32426a4c9492244fb1c432b9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071893"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager (clase)

Administra menús con barra desplazable. Un menú con barra desplazable es un menú de la barra de menús. El usuario puede quitar un menú con barra desplazable de la barra de menús y provocar que el menú con barra desplazable quede flotante.

   Para obtener más información, vea el código fuente ubicado en el **VC\\atlmfc\\src\\mfc** carpeta de la instalación de Visual Studio.

## <a name="syntax"></a>Sintaxis

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Construye un objeto `CMenuTearOffManager`.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CMenuTearOffManager::Build](#build)||
|[CMenuTearOffManager::GetRegPath](#getregpath)||
|[CMenuTearOffManager::Initialize](#initialize)|Inicializa un `CMenuTearOffManager` objeto.|
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||
|[CMenuTearOffManager::Parse](#parse)||
|[CMenuTearOffManager::Reset](#reset)||
|[CMenuTearOffManager::SetInUse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>Comentarios

Para poder utilizar menús desplazable en la aplicación, debe tener un `CMenuTearOffManager` objeto. En la mayoría de los casos, no crear ni inicializar un `CMenuTearOffManager` objeto directamente. Esto se controla automáticamente cuando se llama a la [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) función.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo construir e inicializar un `CMenuTearOffManager` objeto mediante una llamada a la `CWinAppEX::EnableTearOffMenus` método. Este fragmento de código forma parte del [ejemplo de WordPad](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>Requisitos

**Encabezado:** afxmenutearoffmanager.h

##  <a name="build"></a>  CMenuTearOffManager::Build

```
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>Parámetros

[in] *uiTearOffBarID*<br/>

[in] *strText*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager

Construye un [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) objeto.

```
CMenuTearOffManager();
```

### <a name="remarks"></a>Comentarios

En la mayoría de los casos, no debería crear un `CMenuTearOffManager` manualmente. El marco de la aplicación crea el `CMenuTearOffManager` objeto cuando se llama a [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).

##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>Valor devuelto

### <a name="remarks"></a>Comentarios

##  <a name="initialize"></a>  CMenuTearOffManager::Initialize

Inicializa un [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) objeto.

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>Parámetros

*lpszRegEntry*<br/>
[in] Una cadena que contiene la ruta de acceso de una entrada del registro. Las aplicaciones se almacena la configuración de barras desplazable en esta entrada del registro.

*uiTearOffMenuFirst*<br/>
[in] El primer identificador de menú para un menú desplazable.

*uiTearOffMenuLast*<br/>
[in] El último identificador de menú para un menú desplazable.

### <a name="return-value"></a>Valor devuelto

Si es correcta, su valor es distinto de cero. En caso contrario, es cero.

### <a name="remarks"></a>Comentarios

El intervalo de identificadores de menú de *uiTearOffMenuFirst* a *uiTearOffMenuLast* debe ser un intervalo continuo. El intervalo define el número de menús desplazable que puede aparecer al mismo tiempo en la aplicación.

##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>Parámetros

[in] *uiID*<br/>

### <a name="return-value"></a>Valor devuelto

### <a name="remarks"></a>Comentarios

##  <a name="parse"></a>  CMenuTearOffManager::Parse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>Parámetros

[in] *str*<br/>

### <a name="return-value"></a>Valor devuelto

### <a name="remarks"></a>Comentarios

##  <a name="reset"></a>  CMenuTearOffManager::Reset

```
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>Parámetros

[in] *hmenu*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse

```
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>Parámetros

[in] *uiCmdId*<br/>

[in] *bUtilice*<br/>

### <a name="remarks"></a>Comentarios

##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus

```
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>Parámetros

[in] *hMenu*<br/>

### <a name="remarks"></a>Comentarios

## <a name="see-also"></a>Vea también

[Gráfico de jerarquías](../../mfc/hierarchy-chart.md)<br/>
[Clases](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx (clase)](../../mfc/reference/cwinappex-class.md)
