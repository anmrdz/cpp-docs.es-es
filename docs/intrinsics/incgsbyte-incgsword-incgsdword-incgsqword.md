---
title: __incgsbyte, __incgsword, __incgsdword, __incgsqword | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __incgsdword
- __incgsqword_cpp
- __incgsword_cpp
- __incgsword
- __incgsbyte
- __incgsbyte_cpp
- __incgsqword
- __incgsdword_cpp
dev_langs:
- C++
helpviewer_keywords:
- __incgsbyte intrinsic
- __incgsword intrinsic
- __incgsqword intrinsic
- __incgsdword intrinsic
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56cdce805e2048cff22007a89da42c736dd14fd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373295"
---
# <a name="incgsbyte-incgsword-incgsdword-incgsqword"></a>__incgsbyte, __incgsword, __incgsdword, __incgsqword

**Específicos de Microsoft**

Agregue uno para el valor en una ubicación de memoria especificada por un desplazamiento relativo al principio de la `GS` segmento.

## <a name="syntax"></a>Sintaxis

```
void __incgsbyte( 
   unsigned long Offset 
);
void __incgsword( 
   unsigned long Offset 
);
void __incgsdword( 
   unsigned long Offset
);
void __incgsqword( 
   unsigned long Offset 
);
```

#### <a name="parameters"></a>Parámetros

*Desplazamiento*<br/>
[in] El desplazamiento desde el principio del `GS`.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__incgsbyte`|x64|
|`__incgsword`|x64|
|`__incgsdword`|x64|
|`__incgsqword`|x64|

## <a name="remarks"></a>Comentarios

Estas funciones intrínsecas solo están disponibles en modo kernel, y las rutinas solo están disponibles como intrínsecos.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[__addgsbyte, \__addgsword, \__addgsdword, \__addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)<br/>
[__readgsbyte, \__readgsdword, \__readgsqword, \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)