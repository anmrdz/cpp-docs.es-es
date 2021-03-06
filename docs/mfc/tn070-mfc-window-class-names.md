---
title: 'TN070: Nombres de clase de ventana MFC | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.classes
dev_langs:
- C++
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92dcc2509732472774a119dafb43174895247948
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382523"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: Nombres de clases de ventana

> [!NOTE]
>  La nota técnica siguiente no se ha actualizado desde que se incluyó por primera vez en la documentación en línea. Como resultado, algunos procedimientos y temas podrían estar obsoletos o ser incorrectos. Para obtener información más reciente, se recomienda buscar el tema de interés en el índice de la documentación en línea.

Windows MFC utilizan un nombre de clase creado dinámicamente que refleja las características de la ventana. MFC genera nombres de clase dinámicamente para ventanas de marco, vistas y ventanas emergentes producidos por la aplicación. Cuadros de diálogo y controles generados por una aplicación MFC tienen el nombre proporcionado por Windows para la clase de ventana en cuestión.

Puede reemplazar el nombre de clase proporcionado dinámicamente mediante el registro de su propia clase de ventana y usarlo en un reemplazo de [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). Sus nombres de clase proporcionado por MFC encajar en uno de los dos formatos siguientes:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

Los dígitos hexadecimales que reemplacen el `%x` caracteres rellenan los datos desde el [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) estructura. MFC utiliza esta técnica para que varias clases de C++ que requieren idénticos **WNDCLASS** estructuras pueden compartir la misma clase de ventana registrada. A diferencia de la mayoría de aplicaciones Win32 simple, las aplicaciones de MFC tienen solo una **WNDPROC**, por lo que puede compartir fácilmente **WNDCLASS** estructuras para ahorrar tiempo y memoria. Los valores pueden reemplazables para el `%x` caracteres que se muestran anteriormente son los siguientes:

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

El primer formulario (`Afx:%x:%x`) se utiliza cuando **hCursor**, **hbrBackground**, y **hIcon** son todas **NULL**.

## <a name="see-also"></a>Vea también

[Notas técnicas por número](../mfc/technical-notes-by-number.md)<br/>
[Notas técnicas por categoría](../mfc/technical-notes-by-category.md)<br/>
[TN020: Convenciones de nomenclatura y numeración de identificadores](../mfc/tn020-id-naming-and-numbering-conventions.md)

