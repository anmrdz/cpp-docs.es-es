---
title: Adición o eliminación de un recurso de cadena (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b3800a99a6c3ae22b34f1c70a7a688ae523b7a67
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061647"
---
# <a name="adding-or-deleting-a-string-resource-c"></a>Adición o eliminación de un recurso de cadena (C++)

Puede insertar rápidamente nuevas entradas en la tabla de la cadena mediante la **cadena** editor. Nuevas cadenas se colocan al final de la tabla y reciben el siguiente identificador disponible. Se puede editar el **ID**, **valor**, o **título** propiedades en el [ventana propiedades](/visualstudio/ide/reference/properties-window) según sea necesario.

El **cadena** editor se asegura de que no use un identificador que ya está en uso. Si selecciona un identificador ya en uso, el **cadena** le notificaremos editor y, a continuación, asignar un identificador genérico único, por ejemplo `IDS_STRING58113`.

### <a name="to-add-a-string-table-entry"></a>Para agregar una entrada de tabla de cadenas

1. Abra la tabla de cadenas haciendo doble clic en el icono correspondiente en [vista de recursos](../windows/resource-view-window.md).

   > [!NOTE]
   > Si el proyecto no contuviera un archivo .rc, vea [Crear un nuevo archivo de script de recursos](../windows/how-to-create-a-resource-script-file.md).

2. Haga doble clic en la tabla de cadenas y elija **nueva cadena** en el menú contextual.

3. En el **cadena** editor, seleccione un **ID** en la lista de identificadores de lista desplegable o escriba directamente en un lugar de identificador.

4. Editar el **valor**, si es necesario.

5. Escriba una entrada para el **título**.

   > [!NOTE]
   > No se permiten cadenas nulas en las tablas de cadenas de Windows. Si crea una entrada en la tabla de cadenas es una cadena nula, recibirá un mensaje pidiéndole que "Especifique una cadena para esta entrada de tabla".

### <a name="to-delete-a-string-table-entry"></a>Para eliminar una entrada de tabla de cadenas

1. Seleccione la entrada que quiera eliminar.

2. En el **editar** menú, haga clic en **eliminar**.

\- o -

- Haga clic en la cadena que desea eliminar y elija **eliminar** en el menú contextual.

\- o -

- Presione el **eliminar** clave.

Para obtener información sobre cómo agregar recursos a proyectos administrados (aquellos que tienen como destino common language runtime), consulte [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [Tutorial: adaptar Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Editor de cadenas](../windows/string-editor.md)