---
title: Clase de valor sizet | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs:
- C++
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b78d205956f026fe730848afa4c0d6fe7b52b52c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102007"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT (Clase de valor)

Representa el tamaño de un objeto. SizeT es un tipo de datos sin signo.

## <a name="syntax"></a>Sintaxis

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Miembros

|Miembro|Descripción|
|------------|-----------------|
|[SizeT::SizeT (Constructor)](#ctor)|Inicializa una nueva instancia de la clase con el valor especificado.|

### <a name="requirements"></a>Requisitos

**Cliente mínimo admitido:** Windows 8

**Servidor mínimo admitido:** Windows Server 2012

**Espacio de nombres:** Plataforma

**Metadatos:** platform.winmd

## <a name="ctor"></a>  Constructor de Sizet

Inicializa una nueva instancia de SizeT con el valor especificado.

### <a name="syntax"></a>Sintaxis

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parámetros

*Valor1*<br/>
Un valor sin signo de 32 bits.

*Value2*<br/>
Puntero a un valor sin signo de 32 bits.

## <a name="see-also"></a>Vea también

[Espacio de nombres de plataforma](../cppcx/platform-namespace-c-cx.md)