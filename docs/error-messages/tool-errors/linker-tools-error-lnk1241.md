---
title: Las herramientas del vinculador LNK1241 Error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1241
dev_langs:
- C++
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4c11a97dd99515ff7623b77ff31de5fb8577b5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040627"
---
# <a name="linker-tools-error-lnk1241"></a>Error de las herramientas del vinculador LNK1241

archivo de recursos ' resource' ya se especificó

Este error se genera si ejecuta **cvtres** manualmente desde la línea de comandos y si, a continuación, pase el archivo .obj resultante del archivo al vinculador además a otros archivos. res.

Para especificar varios archivos. res, pase todo al vinculador como archivos, no desde los archivos .obj crean por **cvtres**.