---
title: _CIatan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIatan
apilocation:
- msvcr120.dll
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- _CIatan
- CIatan
dev_langs:
- C++
helpviewer_keywords:
- CIatan intrinsic
- _CIatan intrinsic
ms.assetid: 3baa0429-fe46-4bab-8b00-868e2186dc8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac1bb0d9252a02c609b328bc1785e477ed44a763
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234344"
---
# <a name="ciatan"></a>_CIatan

Calcula el arcotangente del valor superior de la pila.

## <a name="syntax"></a>Sintaxis

```
void __cdecl _CIatan();
```

## <a name="remarks"></a>Comentarios

Esta versión de la función `atan` tiene una convención de llamada especializada que el compilador entiende. Acelera la ejecución porque evita que se generen copias y ayuda con la asignación de registros.

El valor resultante se inserta en la parte superior de la pila.

## <a name="requirements"></a>Requisitos

**Plataforma:** x86

## <a name="see-also"></a>Vea también

[Referencia alfabética de funciones](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)