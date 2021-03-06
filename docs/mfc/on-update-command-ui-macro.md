---
title: ON_UPDATE_COMMAND_UI (macro) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_UPDATE_COMMAND_UI
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17111e24a63d527996eadd82c804e5147ad78552
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433470"
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI (Macro)

Use la **propiedades** ventana para conectarse a un objeto de interfaz de usuario a un controlador de actualización de comandos en un objeto de destino del comando. Automáticamente se conectará el Id. del objeto de interfaz de usuario a la macro ON_UPDATE_COMMAND_UI y crear un controlador en el objeto que va a controlar la actualización. Consulte [asignar mensajes a funciones](../mfc/reference/mapping-messages-to-functions.md) para obtener más información.

Por ejemplo, para actualizar un comando Borrar todo en el menú de edición del programa, use la **propiedades** ventana para agregar una entrada de mapa de mensajes en la clase seleccionada, una declaración de función para un controlador de actualización de comandos denominada `OnUpdateEditClearAll` en la clase declaración y una plantilla de función vacíos en el archivo de implementación de la clase. El prototipo de función tiene este aspecto:

[!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]

Al igual que todos los controladores, se muestra en la función la **afx_msg** palabra clave. Al igual que todos los controladores de actualización, toma un argumento, un puntero a un `CCmdUI` objeto.

## <a name="see-also"></a>Vea también

[Procedimiento para actualizar objetos de la interfaz de usuario](../mfc/how-to-update-user-interface-objects.md)

