---
title: __writefsbyte, __writefsdword, __writefsqword, __writefsword | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writefsword
- __writefsbyte
- __writefsqword
- __writefsdword
dev_langs:
- C++
helpviewer_keywords:
- writefsbyte intrinsic
- __writefsword intrinsic
- writefsqword intrinsic
- writefsdword intrinsic
- __writefsdword intrinsic
- __writefsqword intrinsic
- __writefsbyte intrinsic
- writefsword intrinsic
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84d6c614b7d571eea378a8cd093e0cafbee1aa48
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404350"
---
# <a name="writefsbyte-writefsdword-writefsqword-writefsword"></a>__writefsbyte, __writefsdword, __writefsqword, __writefsword

**Específicos de Microsoft**

Escribir en la memoria en una ubicación especificada por un desplazamiento relativo al principio del segmento de FS.

## <a name="syntax"></a>Sintaxis

```
void __writefsbyte( 
   unsigned long Offset, 
   unsigned char Data 
);
void __writefsword( 
   unsigned long Offset, 
   unsigned short Data 
);
void __writefsdword( 
   unsigned long Offset, 
   unsigned long Data 
);
void __writefsqword( 
   unsigned long Offset, 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Parámetros

*Desplazamiento*<br/>
[in] El desplazamiento desde el principio de FS para escribir en.

*Data*<br/>
[in] El valor para escribir.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__writefsbyte`|x86|
|`__writefsword`|x86|
|`__writefsdword`|x86|
|`__writefsqword`|x86|

**Archivo de encabezado** \<intrin.h >

## <a name="remarks"></a>Comentarios

Estas rutinas sólo están disponibles como intrínsecos.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)