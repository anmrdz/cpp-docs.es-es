---
title: __outword | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outword
dev_langs:
- C++
helpviewer_keywords:
- __outword intrinsic
- out instruction
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eac50ba9c4c1b4bc14ebb847b283b5c2da11605e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388803"
---
# <a name="outword"></a>__outword

**Específicos de Microsoft**

Genera el `out` instrucción, que envía la palabra `Data` fuera del puerto de E/S especificado por `Port`.

## <a name="syntax"></a>Sintaxis

```
void __outword( 
   unsigned short Port, 
   unsigned short Data 
);
```

#### <a name="parameters"></a>Parámetros

*Puerto*<br/>
[in] El puerto para enviar los datos.

*Data*<br/>
[in] Los datos se envíen.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__outword`|x86, x64|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

Esta rutina solo está disponible como función intrínseca.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)