---
title: __readcr0 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readcr0
dev_langs:
- C++
helpviewer_keywords:
- __readcr0 intrinsic
ms.assetid: 25bdb093-d83c-48d7-9c0f-224de8e2c61c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f989c7bd6cc74a688e8694ed59899c59c50cb0d4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430662"
---
# <a name="readcr0"></a>__readcr0

**Específicos de Microsoft**

Lee el registro CR0 y devuelve su valor.

## <a name="syntax"></a>Sintaxis

```
unsigned long __readcr0(void);  /* X86 */
unsigned __int64 __readcr0(void);  /* X64 */

```

## <a name="return-value"></a>Valor devuelto

El valor del registro CR0.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__readcr0`|x86, x64|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

Este intrínseco solo está disponible en modo kernel, y la rutina solo está disponible como intrínseco.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)