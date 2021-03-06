---
title: Las herramientas del vinculador LNK1120 Error | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1120
dev_langs:
- C++
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea6cc7fdde3d68c9b00ba60c7fa650cbdfd3bd8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086348"
---
# <a name="linker-tools-error-lnk1120"></a>Error de las herramientas del vinculador LNK1120

> *número* externos sin resolver

El error LNK1120 notifica el recuento (*número*) de los errores de símbolo externo sin resolver de esta operación de enlace. La mayoría sin resolver errores de símbolo externo se notifican individualmente por [Error de las herramientas del vinculador LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) y [Error de las herramientas del vinculador LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), que preceden a este mensaje de error, una vez para cada externo sin resolver error de símbolo.

Para corregir este error, corrija todos los demás errores externos sin resolver o de otros errores del vinculador que lo preceden en la salida de compilación. No se notifica este error cuando no hay errores externos sin resolver permanecen.
