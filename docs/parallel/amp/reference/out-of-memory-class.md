---
title: out_of_memory (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
dev_langs:
- C++
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3da944d519964105bd43135d61b5874ad96a6670
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378830"
---
# <a name="outofmemory-class"></a>out_of_memory (clase)

La excepción se produce cuando un método produce un error debido a la falta de memoria del sistema o del dispositivo.

## <a name="syntax"></a>Sintaxis

```
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[out_of_memory (Constructor)](#ctor)|Inicializa una nueva instancia de la clase `out_of_memory`.|

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Requisitos

**Encabezado:** amprt.h

**Espacio de nombres:** Concurrency
## <a name="ctor"></a> out_of_memory)

Inicializa una nueva instancia de la clase.

### <a name="syntax"></a>Sintaxis

```
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>Parámetros

*_Cuerpo*<br/>
Descripción del error.

### <a name="return-value"></a>Valor devuelto

Nueva instancia de la clase `out_of_memory`.

## <a name="see-also"></a>Vea también

[Espacio de nombres de simultaneidad (C++ AMP)](concurrency-namespace-cpp-amp.md)
