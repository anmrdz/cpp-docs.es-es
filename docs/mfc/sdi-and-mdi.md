---
title: SDI y MDI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8189af7939bfca0fd206fa72892098e373444879
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401451"
---
# <a name="sdi-and-mdi"></a>SDI y MDI

MFC facilita trabajar con la interfaz de único documento (SDI) y las aplicaciones de interfaz de múltiples documentos (MDI).

Las aplicaciones SDI permiten sólo una ventana de marco de documento abierto a la vez. Las aplicaciones MDI permiten documento varias ventanas de marco esté abierto en la misma instancia de una aplicación. Una aplicación MDI tiene una ventana dentro de lo múltiples MDI, se pueden abrir ventanas secundarias, que son ventanas de marco a sí mismos, que contiene un documento independiente. En algunas aplicaciones, las ventanas secundarias pueden ser de tipos diferentes, como chart de windows y windows de la hoja de cálculo. En ese caso, puede cambiar la barra de menús que se activan ventanas secundarias MDI de diferentes tipos.

> [!NOTE]
>  En Windows 95 y versiones posteriores, las aplicaciones normalmente son SDI porque el sistema operativo ha adoptado una vista "centrado en documentos".

Para obtener más información, consulte [documentos, vistas y el marco de trabajo](../mfc/documents-views-and-the-framework.md).

## <a name="see-also"></a>Vea también

[Uso de las clases para escribir aplicaciones para Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
