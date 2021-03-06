---
title: Especificar los niveles de funcionalidad | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 765a5293f233cb6df0654416ea2a5463df1095a8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054428"
---
# <a name="specifying-levels-of-functionality"></a>Especificar los niveles de funcionalidad

En este artículo se describe cómo agregar los siguientes niveles de funcionalidad a su [CObject](../mfc/reference/cobject-class.md)-clase derivada:

- [Información de clases en tiempo de ejecución](#_core_to_add_run.2d.time_class_information)

- [Compatibilidad con la creación dinámica](#_core_to_add_dynamic_creation_support)

- [Compatibilidad con la serialización](#_core_to_add_serialization_support)

Para obtener una descripción general de `CObject` funcionalidad, consulte el artículo [derivar una clase de CObject](../mfc/deriving-a-class-from-cobject.md).

- [Información de clases en tiempo de ejecución](#_core_to_add_run.2d.time_class_information)
#### <a name="_core_to_add_run.2d.time_class_information"></a> Para agregar información de clases en tiempo de ejecución

1. Derive la clase de `CObject`, tal y como se describe en el [derivar una clase de CObject](../mfc/deriving-a-class-from-cobject.md) artículo.

1. Utilice la macro DECLARE_DYNAMIC en la declaración de clase, como se muestra aquí:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Utilice la macro IMPLEMENT_DYNAMIC en el archivo de implementación (. (CPP) de la clase. Esta macro toma como argumentos el nombre de la clase y su clase base, como sigue:

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
>  Coloque siempre IMPLEMENT_DYNAMIC en el archivo de implementación (. (CPP) de la clase. La macro IMPLEMENT_DYNAMIC debe evaluarse en una sola vez durante una compilación y, por tanto, no debe usarse en un archivo de interfaz (. (H) que potencialmente podría incluirse en más de un archivo.

#### <a name="_core_to_add_dynamic_creation_support"></a> Para agregar compatibilidad con la creación dinámica

1. Derive la clase de `CObject`.

1. Utilice la macro DECLARE_DYNCREATE en la declaración de clase.

1. Definir un constructor sin argumentos (un constructor predeterminado).

1. Utilice la macro IMPLEMENT_DYNCREATE en el archivo de implementación de clase.

#### <a name="_core_to_add_serialization_support"></a> Para agregar compatibilidad con la serialización

1. Derive la clase de `CObject`.

1. Invalidar el `Serialize` función miembro.

    > [!NOTE]
    >  Si se llama a `Serialize` directamente, es decir, no desea serializar el objeto a través de un puntero polimórfico, omita los pasos 3 a 5.

1. Utilice la macro DECLARE_SERIAL en la declaración de clase.

1. Definir un constructor sin argumentos (un constructor predeterminado).

1. Utilice la macro IMPLEMENT_SERIAL en el archivo de implementación de clase.

> [!NOTE]
>  Un "puntero polimórfico" apunta a un objeto de una clase (llamar A) o a un objeto de cualquier clase derivada de una (por ejemplo, B). Para serializar a través de un puntero polimórfico, el marco de trabajo debe determinar la clase de tiempo de ejecución del objeto que se está serializando (B), ya que podría ser un objeto de cualquier clase derivada de alguna clase base (A).

Para obtener más información sobre cómo habilitar la serialización al derivar la clase de `CObject`, consulte los artículos [archivos en MFC](../mfc/files-in-mfc.md) y [serialización](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Vea también

[Derivación de una clase de CObject](../mfc/deriving-a-class-from-cobject.md)
