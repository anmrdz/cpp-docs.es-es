---
title: Derivado de mapas de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a1bb9b05a6d3149e7bb6ac5e472652b499ff22c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416154"
---
# <a name="derived-message-maps"></a>Mapas de mensajes derivados

Durante el control de mensajes, comprobación de un mensaje de la clase map no es el final de la historia de mapa de mensajes. ¿Qué ocurre si clase `CMyView` (derivado de `CView`) no tiene ninguna entrada coincidente para un mensaje

Tenga en cuenta que `CView`, la clase base de `CMyView`, se deriva a su vez `CWnd`. Por lo tanto `CMyView` *es* un `CView` y *es* un `CWnd`. Cada una de esas clases tiene su propio mapa de mensajes. La figura "Una jerarquía de vistas" a continuación se muestra la relación jerárquica de las clases, pero tenga en cuenta que un `CMyView` objeto es un objeto único que tiene las características de las tres clases.

![Jerarquía de una vista](../mfc/media/vc38621.gif "vc38621") una jerarquía de vistas

Por tanto, si no se puede asociar un mensaje en la clase `CMyView`del mapa de mensajes, el marco de trabajo busca en el mapa de mensajes de su clase base inmediata. El `BEGIN_MESSAGE_MAP` macro al principio del mapa de mensajes especifica dos nombres de clase como argumentos:

[!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]

El primer argumento nombra la clase a la que pertenece el mapa de mensajes. El segundo argumento proporciona una conexión con la clase base inmediata: `CView` aquí, por lo que el marco de trabajo puede buscar su mapa de mensajes, demasiado.

Los controladores de mensajes proporcionados en una clase base, por tanto, heredan la clase derivada. Esto es muy similar a las funciones miembro virtuales normales sin necesidad de realizar todas las funciones miembro de controlador virtual.

Si se encuentra ningún controlador en cualquiera de los mapas de mensajes de la clase base, se realiza el procesamiento predeterminado del mensaje. Si el mensaje es un comando, el marco de trabajo lo enruta al destino del comando siguiente. Si es un mensaje estándar de Windows, el mensaje se pasa al procedimiento de ventana predeterminado adecuado.

Para acelerar la búsqueda de mapas de mensajes, el marco de trabajo almacena en caché a recientes coincidencias en la probabilidad de que recibirá el mismo mensaje nuevo. Una consecuencia de esto es que los procesos de framework no controlan mensajes bastante eficaz. Mapas de mensajes son también más espacio-eficaces que las implementaciones que usan funciones virtuales.

## <a name="see-also"></a>Vea también

[Cómo busca el marco los mapas de mensajes](../mfc/how-the-framework-searches-message-maps.md)

