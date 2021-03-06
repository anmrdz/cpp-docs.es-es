---
title: 'Portapapeles: Agregar otros formatos | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f2a34228a6e6b0c0d4f1800142e657a462aa095
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402010"
---
# <a name="clipboard-adding-other-formats"></a>Portapapeles: Agregar otros formatos

En este tema se explica cómo expandir la lista de formatos admitidos, especialmente para la compatibilidad con OLE. El tema [Portapapeles: copiar y pegar datos](../mfc/clipboard-copying-and-pasting-data.md) describe la implementación mínima necesaria para admitir copiando y pegando mediante el Portapapeles. Si esto es todo lo que implemente, son los únicos formatos que se coloca en el Portapapeles **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**y posiblemente **CF_LINKSOURCE**. La mayoría de las aplicaciones necesitará más formatos del Portapapeles que estos tres.

##  <a name="_core_registering_custom_formats"></a> Registrar formatos personalizados

Para crear sus propios formatos personalizados, siga el mismo procedimiento que utilizaría para registrar cualquier formato de Portapapeles personalizado: pase el nombre de formato que desea la **RegisterClipboardFormat** funcionar y utilizar su valor devuelto como el identificador de formato.

##  <a name="_core_placing_formats_on_the_clipboard"></a> Colocar formatos en el Portapapeles

Para agregar más formatos a los que se encuentran en el Portapapeles, se debe reemplazar el `OnGetClipboardData` función de la clase que deriva de cualquiera `COleClientItem` o `COleServerItem` (dependiendo de si los datos que se van a copiarse están nativos). En esta función, debe utilizar el siguiente procedimiento.

#### <a name="to-place-formats-on-the-clipboard"></a>Para colocar formatos en el Portapapeles

1. Crear un objeto `COleDataSource`.

1. Pase este origen de datos a una función que agrega sus formatos de datos nativo a la lista de formatos compatibles mediante una llamada a `COleDataSource::CacheGlobalData`.

1. Agregar los formatos estándar mediante una llamada a `COleDataSource::CacheGlobalData` para cada formato estándar que desee admitir.

Esta técnica se usa en el programa de ejemplo OLE de MFC [HIERSVR](../visual-cpp-samples.md) (examine el `OnGetClipboardData` función miembro de la **CServerItem** clase). La única diferencia en este ejemplo es que el paso tres no está implementado porque HIERSVR es compatible con ningún otros formatos estándares.

### <a name="what-do-you-want-to-know-more-about"></a>¿Qué desea saber más sobre

- [Transferencia de datos uniformes y orígenes de datos y objetos de datos OLE](../mfc/data-objects-and-data-sources-ole.md)

- [Arrastrar y colocar OLE](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Vea también

[Portapapeles: Usar el mecanismo del Portapapeles de OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

