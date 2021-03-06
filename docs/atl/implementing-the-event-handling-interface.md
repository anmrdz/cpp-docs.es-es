---
title: Implementar la interfaz de control de eventos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 57e685ea9ac4b1efc76f7657421d825b83f4a9b7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078627"
---
# <a name="implementing-the-event-handling-interface"></a>Implementar la interfaz de control de eventos

ATL le ayuda con los tres elementos necesarios para controlar los eventos: implementar la interfaz de eventos, que avisa de origen del evento y desaconsejar el origen del evento. Los pasos precisos que deberá tomar dependen del tipo de la interfaz de eventos y los requisitos de rendimiento de la aplicación.

Las formas más comunes de implementación de una interfaz mediante ATL son:

- Derivar directamente desde una interfaz personalizada.

- Derivar de [IDispatchImpl](../atl/reference/idispatchimpl-class.md) para interfaces duales descritas en una biblioteca de tipos.

- Derivar de [IDispEventImpl](../atl/reference/idispeventimpl-class.md) para interfaces dispinterface descrito en una biblioteca de tipos.

- Derivar de [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) para interfaces dispinterface no se describen en una biblioteca de tipos o cuando desea mejorar la eficacia no carga la información de tipo en tiempo de ejecución.

Si está implementando una interfaz dual o personalizada, debe aconsejar el origen de eventos mediante una llamada a [AtlAdvise](reference/connection-point-global-functions.md#atladvise) o [¡CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise). Deberá realizar un seguimiento de la cookie devuelta por la llamada. Llame a [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) para interrumpir la conexión.

Si está implementando una interfaz dispinterface utilizando `IDispEventImpl` o `IDispEventSimpleImpl`, debe aconsejar el origen de eventos mediante una llamada a [IDispEventSimpleImpl:: DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Llame a [IDispEventSimpleImpl:: DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) para interrumpir la conexión.

Si usas `IDispEventImpl` como una clase base de un control compuesto, los orígenes de eventos incluidos en el mapa de receptores será aconsejable y deben notificar automáticamente con [CComCompositeControl:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

El `IDispEventImpl` y `IDispEventSimpleImpl` clases administran la cookie para usted.

## <a name="see-also"></a>Vea también

[Control de eventos](../atl/event-handling-and-atl.md)
