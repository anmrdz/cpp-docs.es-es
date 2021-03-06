---
title: Agregar una entrada a una tabla de aceleradores (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e0017e0c4d5462ef985b70b44120ff20066f626
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391805"
---
# <a name="adding-an-entry-to-an-accelerator-table-c"></a>Agregar una entrada a una tabla de aceleradores (C++)

### <a name="to-add-an-entry-to-an-accelerator-table"></a>Para agregar una entrada a una tabla de aceleradores

1. En un proyecto de C++, abra la tabla de aceleradores haciendo doble clic en el icono correspondiente en [vista de recursos](../windows/resource-view-window.md).

   > [!NOTE]
   > Si el proyecto no contuviera un archivo .rc, vea [Crear un nuevo archivo de script de recursos](../windows/how-to-create-a-resource-script-file.md).

2. Haga doble clic en la tabla de aceleradores y elija **nuevo acelerador** en el menú contextual, o haga clic en la entrada de fila vacía en la parte inferior de la tabla.

3. Seleccione un [Id. de](id-property.md) en la lista desplegable en el Id. de cuadro o escriba un nuevo identificador en el **ID** cuadro.

4. Tipo de la [clave](../windows/accelerator-key-property.md) que desea usar como acelerador o contextual y elija **tecla siguiente** en el menú contextual para establecer una combinación de teclas (el **tecla siguiente** comando es También está disponible en el **editar** menú).

5. Cambiar el [modificador](../windows/accelerator-modifier-property.md) y [tipo](../windows/accelerator-type-property.md), si es necesario.

6. Presione **ENTRAR**.

   > [!NOTE]
   > Asegúrese de que todos los aceleradores que defina sean únicos. Puede tener varias combinaciones de teclas asignadas al mismo identificador no tiene ningún efecto negativos, por ejemplo, **Ctrl** + **P** y **F8** pueden asignarse a ID_PRINT. Sin embargo, tener una combinación de teclas asignada a más de un identificador no funcionará bien, por ejemplo, **Ctrl** + **Z** asignado a tanto a ID_SPELL_CHECK como a ID_THESAURUS.

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Edición de tablas de aceleradores](../windows/editing-accelerator-tables.md)<br/>
[Editor de aceleradores](../windows/accelerator-editor.md)