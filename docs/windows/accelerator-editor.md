---
title: Editor de aceleradores (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.accelerator.F1
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42870002ff84b697599443da8ab9b9b88dbbd7ca
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318803"
---
# <a name="accelerator-editor-c"></a>Editor de aceleradores (C++)

Una tabla de aceleradores es un recurso de Windows de C++ que contiene una lista de teclas de aceleración (también conocido como teclas de método abreviado) y los identificadores de comandos que están asociados con ellas. Un programa puede tener más de una tabla de aceleradores.

Normalmente, los aceleradores se usan como métodos abreviados de teclado para comandos de programa que también están disponibles en un menú o una barra de herramientas. Sin embargo, puede usar la tabla de aceleradores para definir las combinaciones de teclas para los comandos que no tienen asociado un objeto de interfaz de usuario.

Puede usar [vista de clases](/visualstudio/ide/viewing-the-structure-of-code) para enlazar comandos de teclas de aceleración al código.

Con el **acelerador** editor, puede:

- [Establecer propiedades de acelerador](../windows/setting-accelerator-properties.md)

- [Asociar una tecla de aceleración a un elemento de menú](../windows/associating-an-accelerator-key-with-a-menu-item.md)

- [Editar tablas de aceleradores](../windows/editing-accelerator-tables.md)

- [Usar teclas de aceleración predefinidas](../windows/predefined-accelerator-keys.md)

   > [!TIP]
   > Al usar el **acelerador** editor, hacer clic en para mostrar un menú contextual de comandos usados con frecuencia. Los comandos disponibles dependen del objeto al que apunta el puntero.

   > [!NOTE]
   > Windows no permite crear tablas de aceleradores vacías. Si crea una tabla de aceleradores sin entradas, se elimina automáticamente al guardar la tabla.

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Editores de recursos](../windows/resource-editors.md)