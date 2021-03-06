---
title: Error recuperable A2008 de ML | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2008
dev_langs:
- C++
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 774cf4c2a51bf084fb63e572cc99b0c8e3cba26f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679380"
---
# <a name="ml-nonfatal-error-a2008"></a>Error recuperable A2008 de ML

**error de sintaxis:**

Un token en la ubicación actual produjo un error de sintaxis.

Puede haberse producido uno de los siguientes:

- Se agregó un prefijo de punto o se omite en una directiva.

- Una palabra reservada (como **C** o **tamaño**) se utiliza como identificador.

- Se utilizó una instrucción que no estaba disponible con la selección actual del procesador o coprocesador.

- Un operador de tiempo de ejecución de comparación (como `==`) se usó en una instrucción condicional de ensamblado en lugar de un operador relacional (como [EQ](../../assembler/masm/operator-eq.md)).

- Una instrucción o la directiva se ha especificado demasiado pocos operandos.

- Se usó una directiva obsoleta.

## <a name="see-also"></a>Vea también

[Mensajes de error de ML](../../assembler/masm/ml-error-messages.md)<br/>