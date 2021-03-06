---
title: _set_SSE2_enable | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_SSE2_enable
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
dev_langs:
- C++
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45f4ed5333dd8ae6bab6291233391884e4efc7ff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407856"
---
# <a name="setsse2enable"></a>_set_SSE2_enable

Habilita o deshabilita el uso de instrucciones de extensiones SIMD de transmisión por secuencias 2 (SSE2) en rutinas matemáticas de CRT. (esta función no está disponible en las arquitecturas x64 porque SSE2 está habilitada de forma predeterminada).

## <a name="syntax"></a>Sintaxis

```C
int _set_SSE2_enable(
   int flag
);
```

### <a name="parameters"></a>Parámetros

*Marca*<br/>
1 para habilitar la implementación de SSE2 y 0 para deshabilitarla. De forma predeterminada, la implementación de SSE2 está habilitada en los procesadores compatibles.

## <a name="return-value"></a>Valor devuelto

Valor distinto de cero si la implementación de SSE2 está habilitada; cero si está deshabilitada.

## <a name="remarks"></a>Comentarios

Las siguientes funciones tienen implementaciones de SSE2 que se pueden habilitar mediante el uso de **_set_SSE2_enable**:

- [atan](atan-atanf-atanl-atan2-atan2f-atan2l.md)

- [ceil](ceil-ceilf-ceill.md)

- [exp](exp-expf.md)

- [floor](floor-floorf-floorl.md)

- [log](log-logf-log10-log10f.md)

- [log10](log-logf-log10-log10f.md)

- [modf](modf-modff-modfl.md)

- [pow](pow-powf-powl.md)

Las implementaciones de SSE2 de estas funciones pueden proporcionar respuestas algo diferentes que las implementaciones predeterminadas, porque los valores intermedios de SSE2 son cantidades de punto flotante de 64 bits, mientras que los valores intermedios de implementación predeterminados son cantidades de punto flotante de 80 bits.

> [!NOTE]
> Si usas el [/Oi (generar funciones intrínsecas)](../../build/reference/oi-generate-intrinsic-functions.md) opción del compilador para compilar el proyecto, puede parecer que **_set_SSE2_enable** no tiene ningún efecto. El **/Oi** opción del compilador indica al compilador la autoridad para usar funciones intrínsecas para reemplazar las llamadas de CRT; este comportamiento invalida el efecto de **_set_SSE2_enable**. Si desea garantizar que **/Oi** no invalida **_set_SSE2_enable**, use **/Oi-** compilar el proyecto. Esto también puede buena práctica cuando se utiliza otros modificadores de compilador que implican **/Oi**.

La implementación de SSE2 solo se usa si se enmascaran todas las excepciones. Use [_control87, _controlfp](control87-controlfp-control87-2.md) para enmascarar las excepciones.

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|
|-------------|---------------------|
|**_set_SSE2_enable**|\<math.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

```C
// crt_set_SSE2_enable.c
// processor: x86
#include <math.h>
#include <stdio.h>

int main()
{
   int i = _set_SSE2_enable(1);

   if (i)
      printf("SSE2 enabled.\n");
   else
      printf("SSE2 not enabled; processor does not support SSE2.\n");
}
```

```Output
SSE2 enabled.
```

## <a name="see-also"></a>Vea también

[Características de la biblioteca CRT](../../c-runtime-library/crt-library-features.md)<br/>
