---
title: Ordenar elementos en el Control de encabezado | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60139821c1b15673fac0fb8f9ec3925cbfa6dc31
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052102"
---
# <a name="ordering-items-in-the-header-control"></a>Ordenar elementos en el control de encabezado

Una vez que haya [agrega elementos a un control de encabezado](../mfc/adding-items-to-the-header-control.md), puede manipular u obtener información sobre el orden con las siguientes funciones:

- [CHeaderCtrl:: GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) y [CHeaderCtrl:: SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

   Recupera y establece el orden de izquierda a derecha de los elementos de encabezado.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

   Recupera el valor de índice para un elemento de encabezado específico.

Además de las funciones de miembro anterior, el estilo HDS_DRAGDROP permite al usuario arrastrar y colocar elementos de encabezado dentro del control de encabezado. Para obtener más información, consulte [que proporciona compatibilidad con arrastrar y colocar elementos de encabezado](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Vea también

[Uso de CHeaderCtrl](../mfc/using-cheaderctrl.md)

