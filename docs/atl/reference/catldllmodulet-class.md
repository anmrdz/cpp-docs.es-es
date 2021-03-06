---
title: CAtlDllModuleT (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 170f46424e8eb4db4c38c91f01a89b53d5cbce0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107834"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT (clase)

Esta clase representa el módulo para un archivo DLL.

## <a name="syntax"></a>Sintaxis

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parámetros

*T*<br/>
La clase derivada de `CAtlDllModuleT`.

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|El constructor.|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Destructor.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Comprueba si se puede descargar el archivo DLL.|
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Devuelve un generador de clases.|
|[CAtlDllModuleT::DllMain](#dllmain)|Punto de entrada opcional en una biblioteca de vínculos dinámicos (DLL).|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Agrega entradas al registro del sistema para los objetos en el archivo DLL.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Quita las entradas del registro del sistema para los objetos en el archivo DLL.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Devuelve un generador de clases. Se invoca por [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Comentarios

`CAtlDllModuleT` representa el módulo para una biblioteca de vínculos dinámicos (DLL) y proporciona funciones usadas por todos los proyectos de archivos DLL. Esta especialización de [CAtlModuleT](../../atl/reference/catlmodulet-class.md) clase incluye compatibilidad para el registro.

Para obtener más información sobre los módulos de ATL, vea [clases de módulo ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Requisitos

**Encabezado:** atlbase.h

##  <a name="catldllmodulet"></a>  CAtlDllModuleT::CAtlDllModuleT

El constructor.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>  CAtlDllModuleT:: ~ CAtlDllModuleT

Destructor.

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>  CAtlDllModuleT::DllCanUnloadNow

Comprueba si se puede descargar el archivo DLL.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Valor devuelto

Devuelve S_OK si se puede descargar el archivo DLL o S_FALSE si no es posible.

##  <a name="dllgetclassobject"></a>  CAtlDllModuleT::DllGetClassObject

Devuelve el generador de clases.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parámetros

*rclsid*<br/>
El CLSID del objeto que se va a crear.

*riid*<br/>
IID de la interfaz solicitada.

*PPV*<br/>
Un puntero al puntero de interfaz identificado por *riid*. Si el objeto no admite esta interfaz, *ppv* se establece en NULL.

### <a name="return-value"></a>Valor devuelto

Devuelve S_OK si se ejecuta correctamente, o un error HRESULT en caso de error.

##  <a name="dllmain"></a>  CAtlDllModuleT::DllMain

Punto de entrada opcional en una biblioteca de vínculos dinámicos (DLL).

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parámetros

*dwReason*<br/>
Si el conjunto de llamadas de notificación DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH y DLL_THREAD_DETACH está deshabilitada.

*lpReserved*<br/>
Reservado.

### <a name="return-value"></a>Valor devuelto

Siempre devuelve TRUE.

### <a name="remarks"></a>Comentarios

Deshabilitar el DLL_THREAD_ATTACH y DLL_THREAD_DETACH notificación de llamadas pueden ser una optimización útil para aplicaciones multiproceso que tiene muchos archivos DLL, que crear y eliminar los subprocesos con frecuencia, y cuyos archivos DLL no necesita estas notificaciones de nivel de subproceso de datos adjuntos o desasociación.

##  <a name="dllregisterserver"></a>  CAtlDllModuleT::DllRegisterServer

Agrega entradas al registro del sistema para los objetos en el archivo DLL.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parámetros

*bRegTypeLib*<br/>
TRUE si la biblioteca de tipos es que se registrarán. El valor predeterminado es TRUE.

### <a name="return-value"></a>Valor devuelto

Devuelve S_OK si se ejecuta correctamente, o un error HRESULT en caso de error.

##  <a name="dllunregisterserver"></a>  CAtlDllModuleT::DllUnregisterServer

Quita las entradas del registro del sistema para los objetos en el archivo DLL.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parámetros

*bUnRegTypeLib*<br/>
TRUE si la biblioteca de tipos se va a quitar del registro. El valor predeterminado es TRUE.

### <a name="return-value"></a>Valor devuelto

Devuelve S_OK si se ejecuta correctamente, o un error HRESULT en caso de error.

##  <a name="getclassobject"></a>  CAtlDllModuleT::GetClassObject

Crea un objeto del CLSID especificado.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parámetros

*rclsid*<br/>
El CLSID del objeto que se va a crear.

*riid*<br/>
IID de la interfaz solicitada.

*PPV*<br/>
Un puntero al puntero de interfaz identificado por *riid*. Si el objeto no admite esta interfaz, *ppv* se establece en NULL.

### <a name="return-value"></a>Valor devuelto

Devuelve S_OK si se ejecuta correctamente, o un error HRESULT en caso de error.

### <a name="remarks"></a>Comentarios

Este método es invocado por [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) y se incluye por compatibilidad con versiones anteriores.

## <a name="see-also"></a>Vea también

[CAtlModuleT (clase)](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT (clase)](../../atl/reference/catlexemodulet-class.md)<br/>
[Información general de clases](../../atl/atl-class-overview.md)<br/>
[Clases de módulo](../../atl/atl-module-classes.md)
