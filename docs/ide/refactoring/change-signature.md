---
title: Cambiar firma | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0007cf50eafa7b61e48b550172eb2d316270c61f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448340"
---
# <a name="change-signature"></a>Cambiar firma
**Qué:** Permite modificar los parámetros de una función.

**Cuándo:** Quiere reordenar, agregar, quitar o modificar los parámetros de una función que actualmente se está usando en varias ubicaciones.

**Por qué:** Podría cambiar el orden de estos parámetros manualmente y, después, buscar todas las llamadas a esa función y cambiarlas una por una, pero esto podría provocar errores.  Esta herramienta de refactorización realizará la tarea automáticamente.

**Cómo**:

1. Coloque el cursor del ratón o texto en el nombre del método que se va a modificar, o bien uno de sus usos:

   ![Código resaltado](images/changesignature_highlight.png)

1. A continuación, realice alguno de los siguientes procedimientos:
   * **Teclado**
     * Presione **Ctrl+R** y después **Ctrl+O**.  (Tenga en cuenta que su método abreviado de teclado puede ser diferente en función del perfil que haya seleccionado).
     * Presione **Ctrl +.** para activar el menú **Acciones rápidas y refactorizaciones** y seleccione **Cambiar firma** en el menú contextual.
   * **Mouse**
     * Seleccione **Editar > Refactorizar > Reordenar parámetros**.
     * Haga clic con el botón derecho en el código, seleccione el menú **Acciones rápidas y refactorizaciones** y elija **Cambiar firma** en el menú contextual.

1. En el cuadro de diálogo **Cambiar firma** que aparece, puede usar los botones a la derecha para cambiar la firma del método:

   ![Cuadro de diálogo para cambiar firma](images/changesignature_dialog.png)

   | Botón | Descripción
   | ------ | ---
   | **Up/Down**    | Mueve el parámetro seleccionado hacia arriba y hacia abajo en la lista.
   | **Add**        | Agrega un parámetro a nuevo la lista
   | **Remove**     | Quita el parámetro seleccionado de la lista.
   | **Modificar**     | Modifica el parámetro seleccionado, cambiando su tipo, nombre y si es opcional, y cuál debería ser su valor insertado.
   | **Revertir**     | Restaura el parámetro seleccionado a su estado original.
   | **Revertir todo** | Restaura todos los parámetros a su estado original.

   > [!TIP]
   > Use la casilla **Omitir la vista previa de los cambios de referencia si todas las referencias están confirmadas,** para realizar los cambios de manera inmediata sin que primero se abra la ventana de vista previa.

   Al agregar o modificar un parámetro, verá la ventana **Agregar parámetro** o **Editar parámetro**.

   ![Agregar o modificar parámetros](images/changesignature_addmodify.png)

   Aquí, puede realizar lo siguiente:

   | Entrada | Descripción
   | ----- | ---
   | **Type**               | El tipo del parámetro (int, double, float, etc.)
   | **Name**               | El nombre del parámetro.
   | **Parámetro opcional** | Hace que el parámetro se especifique de manera opcional.
   | **Valor insertado**     | El valor insertado en las llamadas a la función donde no se especifica el parámetro (solo es válido para **Agregar**).
   | **Valor predeterminado**      | El valor que usa la función si el autor de la llamada no especifica ninguno (solo es válido para **Parámetros opcionales**).

1. Use la lista desplegable **Ámbito de búsqueda** para seleccionar si los cambios se van a aplicar al proyecto o a toda la solución.

1. Cuando haya terminado, presione el botón **Aceptar** para realizar los cambios.  Asegúrese de que los cambios que está solicitando se están realizando de manera correcta.  Use las casillas de la mitad superior de la ventana para habilitar o deshabilitar el cambio de nombre de cualquier elemento.

   ![Vista previa del cambio de firma](images/changesignature_preview.png)

1. Cuando todo parezca correcto, haga clic en el botón **Aplicar** y la función se cambiará en el código fuente.

   ![Resultado del cambio de firma](images/changesignature_result.png)