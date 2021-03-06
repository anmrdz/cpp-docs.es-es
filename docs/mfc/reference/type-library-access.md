---
title: Tipo de acceso a la biblioteca | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a361c1e50945b19562082424c178a21191bd0b9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404747"
---
# <a name="type-library-access"></a>Acceso a la biblioteca de tipos

Bibliotecas de tipos exponen las interfaces de un control OLE para otras aplicaciones compatibles con OLE. Cada control OLE debe tener una biblioteca de tipos si una o más interfaces deben exponerse.

Las macros siguientes permiten un control OLE proporcionar acceso a su propia biblioteca de tipos:

### <a name="type-library-access"></a>Acceso a la biblioteca de tipos

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Declara un `GetTypeLib` función miembro de un control OLE (debe usarse en la declaración de clase).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implementa un `GetTypeLib` función miembro de un control OLE (debe usarse en la implementación de la clase).|

##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB

Declara el `GetTypeLib` función miembro de la clase del control.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Parámetros

*CLASS_NAME*<br/>
El nombre de la clase de control relacionada con la biblioteca de tipos.

### <a name="remarks"></a>Comentarios

Use esta macro en el archivo de encabezado de la clase de control.

### <a name="requirements"></a>Requisitos

**Encabezado:** afxdisp.h

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB

Implementa el control `GetTypeLib` función miembro.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Parámetros

*CLASS_NAME*<br/>
El nombre de la clase de control relacionada con la biblioteca de tipos.

*tlid*<br/>
El número de Id. de la biblioteca de tipos.

*wVerMajor*<br/>
El número de versión principal de biblioteca de tipos.

*wVerMinor*<br/>
El número de versión secundaria de biblioteca de tipos.

### <a name="remarks"></a>Comentarios

Esta macro debe aparecer en el archivo de implementación para cualquier clase de control que utiliza el declare_oletypelib (macro).

### <a name="requirements"></a>Requisitos

**Encabezado:** afxdisp.h

## <a name="see-also"></a>Vea también

[Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md)
