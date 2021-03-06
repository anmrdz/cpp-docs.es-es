---
title: Uso de un Control de tecla de acceso frecuente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be0d27016204724672c23f04fdee38f01b69e6a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372295"
---
# <a name="using-a-hot-key-control"></a>Usar un control de tecla de acceso rápido

Uso típico de un control de tecla de acceso frecuente, sigue el patrón siguiente:

- Se crea el control. Si el control se especifica en una plantilla de cuadro de diálogo, creación es automática cuando se crea el cuadro de diálogo. (Debe tener un [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) miembro en la clase de cuadro de diálogo que se corresponde con el control de tecla de acceso frecuente.) Como alternativa, puede usar el [crear](../mfc/reference/chotkeyctrl-class.md#create) función miembro para crear el control como una ventana secundaria de cualquier ventana.

- Si desea establecer un valor predeterminado para el control, llame a la [función miembro SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) función miembro. Si desea prohibir ciertos Estados MAYÚS, llame a [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). Para los controles en un cuadro de diálogo, un buen momento para hacerlo es en el cuadro de diálogo [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) función.

- El usuario interactúa con el control presionando una combinación de teclas de acceso rápida cuando el control de tecla de acceso frecuente tiene el foco. El usuario, a continuación, algún modo indica que esta tarea se ha completado, quizás haciendo clic en un botón en el cuadro de diálogo.

- Cuando se notifica al programa que el usuario ha seleccionado una tecla de acceso rápido, debe utilizar la función miembro [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) para recuperar los valores de estado clave- and -shift virtuales desde el control de tecla de acceso frecuente.

- Una vez que conoce la clave que el usuario seleccionado, puede establecer la tecla de acceso rápido mediante uno de los métodos descritos en [establecer una tecla de acceso rápido](../mfc/setting-a-hot-key.md).

- Si el control de tecla de acceso frecuente se encuentra en un cuadro de diálogo y el `CHotKeyCtrl` automáticamente se destruirá el objeto. Si no, deberá asegurarse de que el control y la `CHotKeyCtrl` objeto se destruyan correctamente.

## <a name="see-also"></a>Vea también

[Uso de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

