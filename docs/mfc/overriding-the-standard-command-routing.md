---
title: Invalidar el enrutamiento de comandos estándar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee603f680919d69684ab94acfa0515d3ec6292
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439502"
---
# <a name="overriding-the-standard-command-routing"></a>Invalidar el enrutamiento de comandos estándar

En raras ocasiones cuando se debe implementar alguna variación del enrutamiento de marco estándar, puede invalidarlo. La idea consiste en cambiar el enrutamiento en una o más clases invalidando `OnCmdMsg` en esas clases. Hacer esto:

- En la clase que interrumpe el orden para pasar a un objeto no predeterminado.

- En el nuevo objeto no predeterminado o en destinos de comando a su vez podría pasar comandos.

Si inserta un nuevo objeto en el enrutamiento, su clase debe ser una clase de destino del comando. En las versiones de reemplazo `OnCmdMsg`, asegúrese de llamar a la versión que está reemplazando. Consulte la [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) función miembro de clase `CCmdTarget` en el *referencia de MFC* y las versiones de clases como `CView` y `CDocument` en el código de origen proporcionado para obtener ejemplos.

## <a name="see-also"></a>Vea también

[Cómo el marco llama a un controlador](../mfc/how-the-framework-calls-a-handler.md)

