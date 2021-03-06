---
title: Uso de una lista de imágenes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dc30d418ae57205e4566dad7f490a773321768e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391675"
---
# <a name="using-an-image-list"></a>Usar una lista de imágenes

Uso típico de una lista de imágenes sigue el patrón siguiente:

- Construir un [CImageList](../mfc/reference/cimagelist-class.md) de objetos y llamar a una de las sobrecargas de su [crear](../mfc/reference/cimagelist-class.md#create) función para crear una lista de imágenes y adjuntarla a la `CImageList` objeto.

- Si no ha agregado imágenes al crear la lista de imágenes, agregar imágenes a la lista de imágenes mediante una llamada a la [agregar](../mfc/reference/cimagelist-class.md#add) o [lectura](../mfc/reference/cimagelist-class.md#read) función miembro.

- Asociar la lista de imágenes con un control mediante una llamada a la función miembro adecuado de ese control, o dibujar imágenes desde la lista de imágenes mediante la lista de imágenes [dibujar](../mfc/reference/cimagelist-class.md#draw) función miembro.

- Quizás permite al usuario arrastrar una imagen, con compatibilidad integrada con la lista de imágenes para arrastrar.

> [!NOTE]
>  Si se creó la lista de imágenes con el **nueva** (operador), deberá destruir la `CImageList` objeto cuando haya terminado con él.

## <a name="see-also"></a>Vea también

[Uso de CImageList](../mfc/using-cimagelist.md)<br/>
[Controles](../mfc/controls-mfc.md)

