---
title: Especificar el Control dominante | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dominant controls
- Dialog Editor [C++], dominant control
- controls [C++], dominant
ms.assetid: 42b523a7-192a-417b-9512-d4af795e002f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31bb19a0854bd28573d474a65781808eaecd7ce2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407574"
---
# <a name="specifying-the-dominant-control"></a>Especificar el control dominante

En primer lugar, el control seleccionado es el control dominante.

### <a name="to-specify-the-dominant-control"></a>Para especificar el control dominante

1. Mantenga presionada la **Ctrl** clave y haga clic en el control que desea usar para influir en el tamaño o la ubicación de otros controles *primera*.

   **Tenga en cuenta** los controladores de tamaño del control dominante son sólidos, mientras que los de los controles subordinados serán huecos. Todos los aún más el cambio de tamaño o la alineación se basa en el control dominante.

### <a name="to-change-the-dominant-control"></a>Para cambiar el control dominante

1. Desactive la selección actual haciendo clic fuera de todos los controles seleccionados actualmente.

2. Repita el procedimiento anterior, seleccione primero un control diferente.

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Selección de varios controles](../windows/selecting-multiple-controls.md)<br/>
[Selección de controles](../windows/selecting-controls.md)<br/>
[Controles de cuadros de diálogo](../windows/controls-in-dialog-boxes.md)