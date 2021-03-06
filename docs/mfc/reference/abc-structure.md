---
title: ABC (estructura) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4f0367e19589093b31fcd64d5312e7b47e8a043
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080278"
---
# <a name="abc-structure"></a>ABC (Estructura)

El `ABC` estructura contiene el ancho de un carácter en una fuente TrueType.

## <a name="syntax"></a>Sintaxis

```
typedef struct _ABC { /* abc */
    int abcA;
    UINT abcB;
    int abcC;
} ABC;
```

#### <a name="parameters"></a>Parámetros

*abcA*<br/>
Especifica el espaciado entre un carácter. El espaciado A es la distancia a agregar a la posición actual antes de dibujar el glifo de caracteres.

*abcB*<br/>
Especifica el espaciado de B del carácter. El espaciado de B es el ancho de la parte dibujar del glifo de caracteres.

*abcC*<br/>
Especifica el espaciado de C del carácter. El espaciado de C es la distancia a agregar a la posición actual para proporcionar a la derecha del glifo de caracteres de espacio en blanco.

## <a name="remarks"></a>Comentarios

El ancho total de un carácter es la suma de los espacios A, B y C. La A o el espacio de C puede ser negativo para indicar underhangs o partes sobresalientes.

## <a name="requirements"></a>Requisitos

**Encabezado:** wingdi.h

## <a name="see-also"></a>Vea también

[Estructuras, estilos, devoluciones de llamada y mapas de mensajes](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

