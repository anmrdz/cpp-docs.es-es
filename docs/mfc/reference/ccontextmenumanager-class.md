---
title: CContextMenuManager (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0890b18316a9b61c3e86858e76176a8d68501852
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082143"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager (clase)

La `CContextMenuManager` objeto administra menús contextuales, también conocidos como menús contextuales.

## <a name="syntax"></a>Sintaxis

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Construye un objeto `CContextMenuManager`.|
|`CContextMenuManager::~CContextMenuManager`|Destructor.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CContextMenuManager::AddMenu](#addmenu)|Agrega un nuevo menú contextual.|
|[CContextMenuManager::GetMenuById](#getmenubyid)|Devuelve un identificador para el menú asociado al identificador de recurso proporcionado.|
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Devuelve un identificador para el menú que coincida con el nombre del menú proporcionado.|
|[CContextMenuManager::GetMenuNames](#getmenunames)|Devuelve una lista de nombres de menú.|
|[CContextMenuManager::LoadState](#loadstate)|Carga los menús contextuales que almacena en el registro de Windows.|
|[CContextMenuManager::ResetState](#resetstate)|Borra los menús contextuales desde el administrador del menú contextual.|
|[CContextMenuManager::SaveState](#savestate)|Guarda los menús contextuales en el registro de Windows.|
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Controles si el `CContextMenuManager` cierra el menú contextual activo cuando muestra un nuevo menú contextual.|
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Muestra el menú contextual especificado.|
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Muestra el menú contextual especificado. Devuelve el índice del comando de menú seleccionado.|

## <a name="remarks"></a>Comentarios

`CContextMenuManager` administra menús contextuales y se asegura de que tienen una apariencia coherente.

No debería crear un `CContextMenuManager` objeto manualmente. El marco de la aplicación crea el `CContextMenuManager` objeto. Sin embargo, debe llamar a [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) cuando se inicializa la aplicación. Después de inicializar el Administrador de contexto, use el método [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) para obtener un puntero para el Administrador de contexto para la aplicación.

Puede crear menús contextuales en tiempo de ejecución mediante una llamada a `AddMenu`. Si desea mostrar el menú sin intervención del usuario receptora primera, llame a `ShowPopupMenu`. `TrackPopupMenu` se utiliza cuando desea crear un menú y esperar la entrada del usuario. `TrackPopupMenu` Devuelve el índice del comando seleccionado o 0 si el usuario ha cerrado sin seleccionar nada.

El `CContextMenuManager` también se puede guardar y cargar su estado en el registro de Windows.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo agregar un menú a un `CContextMenuManager` objeto y no para cerrar el menú emergente activo cuando el `CContextMenuManager` objeto muestra un menú emergente de nuevo. Este fragmento de código forma parte de la [ejemplo Custom Pages](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Requisitos

**Encabezado:** afxcontextmenumanager.h

##  <a name="addmenu"></a>  CContextMenuManager::AddMenu

Agrega un nuevo menú contextual para el [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>Parámetros

*uiMenuNameResId*<br/>
[in] Un identificador de recurso para una cadena que contiene el nombre para el nuevo menú.

*uiMenuResId*<br/>
[in] El identificador de recurso de menú.

*lpszName*<br/>
[in] Una cadena que contiene el nombre para el nuevo menú.

### <a name="return-value"></a>Valor devuelto

Distinto de cero si el método se realizó correctamente; 0 si se produce un error en el método.

### <a name="remarks"></a>Comentarios

Este método produce un error si *uiMenuResId* no es válido o si otro menú con el mismo nombre ya está en el `CContextMenuManager`.

##  <a name="ccontextmenumanager"></a>  CContextMenuManager::CContextMenuManager

Construye un [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) objeto.

```
CContextMenuManager();
```

### <a name="remarks"></a>Comentarios

En la mayoría de los casos, no debería crear un `CContextMenuManager` manualmente. El marco de la aplicación crea el `CContextMenuManager` objeto. Debe llamar a [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) durante la inicialización de la aplicación. Para obtener un puntero para el Administrador de contexto, llame a [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).

##  <a name="getmenubyid"></a>  CContextMenuManager::GetMenuById

Devuelve un identificador para el menú asociado con un identificador de recurso determinado.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Parámetros

*nMenuResId*<br/>
[in] El identificador de recurso para el menú.

### <a name="return-value"></a>Valor devuelto

Un identificador del menú asociado o `NULL` si no se encuentra el menú.

##  <a name="getmenubyname"></a>  CContextMenuManager::GetMenuByName

Devuelve un identificador a un menú específico.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Parámetros

*lpszName*<br/>
[in] Una cadena que contiene el nombre del menú que se va a recuperar.

*puiOrigResID*<br/>
[out] Un puntero a un tipo UINT. Este parámetro contiene el identificador de recurso del menú especificado, si se encuentra.

### <a name="return-value"></a>Valor devuelto

Un identificador del menú que coincide con el nombre que especificó *lpszName*. NULL si no hay ningún menú llamado *lpszName*.

### <a name="remarks"></a>Comentarios

Si este método busca un menú que coincida con *lpszName*, `GetMenuByName` almacena el identificador de recurso de menú en el parámetro *puiOrigResID*.

##  <a name="getmenunames"></a>  CContextMenuManager::GetMenuNames

Devuelve la lista de nombres de menú agregados a la [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parámetros

*listOfNames*<br/>
[out] Una referencia a un [CStringList](../../mfc/reference/cstringlist-class.md) parámetro. Este método escribe la lista de nombres de menú para este parámetro.

##  <a name="loadstate"></a>  CContextMenuManager::LoadState

Carga la información asociada con el [CContextMenuManager (clase)](../../mfc/reference/ccontextmenumanager-class.md) desde el registro de Windows.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parámetros

*lpszProfileName*<br/>
[in] Una cadena que contiene la ruta de acceso relativa de una clave del registro.

### <a name="return-value"></a>Valor devuelto

Distinto de cero si el método es correcto; en caso contrario, es 0.

### <a name="remarks"></a>Comentarios

El *lpszProfileName* parámetro no es la ruta de acceso absoluta para una entrada del registro. Es una ruta de acceso relativa que se agrega al final de la clave del registro de forma predeterminada para la aplicación. Para obtener o establecer la clave del registro de forma predeterminada, utilice los métodos [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) y [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) respectivamente.

Utilice el método [CContextMenuManager::SaveState](#savestate) para guardar los menús contextuales en el registro.

##  <a name="resetstate"></a>  CContextMenuManager::ResetState

Borra todos los elementos desde los menús contextuales asociados con el [CContextMenuManager (clase)](../../mfc/reference/ccontextmenumanager-class.md).

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Valor devuelto

TRUE si el método se realiza correctamente; FALSE si se produce un error.

### <a name="remarks"></a>Comentarios

Este método borra los menús emergentes y los quita de la `CContextMenuManager`.

##  <a name="savestate"></a>  CContextMenuManager::SaveState

Guarda la información asociada con el [CContextMenuManager (clase)](../../mfc/reference/ccontextmenumanager-class.md) en el registro de Windows.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parámetros

*lpszProfileName*<br/>
[in] Una cadena que contiene la ruta de acceso relativa de una clave del registro.

### <a name="return-value"></a>Valor devuelto

Distinto de cero si el método es correcto; en caso contrario, es 0.

### <a name="remarks"></a>Comentarios

El *lpszProfileName* parámetro no es la ruta de acceso absoluta para una entrada del registro. Es una ruta de acceso relativa que se agrega al final de la clave del registro de forma predeterminada para la aplicación. Para obtener o establecer la clave del registro de forma predeterminada, utilice los métodos [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) y [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) respectivamente.

Utilice el método [CContextMenuManager::LoadState](#loadstate) para cargar los menús contextuales del registro.

##  <a name="setdontcloseactivemenu"></a>  CContextMenuManager::SetDontCloseActiveMenu

Controles si el [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) cierra el menú emergente activo cuando se muestre un menú emergente de nuevo.

```
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parámetros

*bSet*<br/>
[in] Un parámetro booleano que controla si se debe cerrar el menú emergente activo. Un valor TRUE indica que no se cierra el menú emergente activo. FALSE indica que se cierra el menú emergente activo.

### <a name="remarks"></a>Comentarios

De forma predeterminada, el `CContextMenuManager` cierra el menú emergente activo.

##  <a name="showpopupmenu"></a>  CContextMenuManager::ShowPopupMenu

Muestra el menú contextual especificado.

```
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bRightAlign = FALSE);

virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bAutoDestroy = TRUE,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Parámetros

*uiMenuResId*<br/>
[in] El identificador de recurso del menú que se mostrará este método.

*x*<br/>
[in] El desplazamiento para el menú contextual, en coordenadas de cliente de horizontal.

*y*<br/>
[in] El desplazamiento vertical para el acceso directo en coordenadas de cliente

*pWndOwner*<br/>
[in] Un puntero a la ventana primaria del menú contextual.

*bOwnMessage*<br/>
[in] Un parámetro booleano que indica cómo se enrutan los mensajes. Si *bOwnMessage* es FALSE, el estándar de MFC se usa el enrutamiento. En caso contrario, *pWndOwner* recibe los mensajes.

*hmenuPopup*<br/>
[in] El identificador del menú que se mostrará este método.

*bAutoDestroy*<br/>
[in] Un parámetro booleano que indica si el menú se eliminará automáticamente.

*bRightAlign*<br/>
[in] Un parámetro booleano que indica cómo se alinean los elementos de menú. Si *bRightAlign* es TRUE, el menú está alineado a la derecha para el orden de lectura de derecha a izquierda.

### <a name="return-value"></a>Valor devuelto

La primera sobrecarga del método devuelve cero si el método muestra el menú correctamente; en caso contrario, es 0. La segunda sobrecarga del método devuelve un puntero a [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) si el menú contextual se muestra correctamente; en caso contrario, NULL.

### <a name="remarks"></a>Comentarios

Este método es similar al método [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) en que ambos métodos mostrar un menú contextual. Sin embargo, `TrackPopupMenu` devuelve el índice del comando de menú seleccionado.

Si el parámetro *bAutoDestroy* es FALSE, deben llamar manualmente a heredadas `DestroyMenu` método para liberar los recursos de memoria. La implementación predeterminada de `ShowPopupMenu` no usa el parámetro *bAutoDestroy*. Se proporciona para su uso futuro o para clases personalizadas derivadas de la `CContextMenuManager` clase.

##  <a name="trackpopupmenu"></a>  CContextMenuManager::TrackPopupMenu

Muestra el menú contextual especificado y devuelve el índice del comando de menú contextual seleccionado.

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Parámetros

*hmenuPopup*<br/>
[in] El identificador del menú contextual que muestra este método.

*x*<br/>
[in] El desplazamiento para el menú contextual, en coordenadas de cliente de horizontal.

*y*<br/>
[in] El desplazamiento para el menú contextual, en coordenadas de cliente vertical.

*pWndOwner*<br/>
[in] Un puntero a la ventana primaria del menú contextual.

*bRightAlign*<br/>
[in] Un parámetro booleano que indica cómo se alinean los elementos de menú. Si *bRightAlign* es TRUE, el menú está alineado a la derecha para el orden de lectura de derecha a izquierda. Si *bRightAlign* es FALSE, el menú está alineado a la izquierda para el orden de lectura de izquierda a derecha.

### <a name="return-value"></a>Valor devuelto

El identificador de comando de menú del comando que el usuario elige; 0 si el usuario cierra el menú contextual sin seleccionar un comando de menú.

### <a name="remarks"></a>Comentarios

Este método funciona como una llamada modal para mostrar un menú contextual. La aplicación no continuará a la siguiente línea de código hasta que el usuario cierra el menú contextual o selecciona un comando. Es un método alternativo que se puede usar para mostrar un menú contextual [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Ese método no es una llamada modal y no devolverá el identificador del comando seleccionado.

## <a name="see-also"></a>Vea también

[Gráfico de jerarquías](../../mfc/hierarchy-chart.md)<br/>
[Clases](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx (clase)](../../mfc/reference/cwinappex-class.md)
