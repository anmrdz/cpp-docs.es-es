---
title: Cambiar un símbolo o el nombre de símbolo (ID) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols [C++], names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 873cf2adc273e5fd39a5680833277ce3790cdfae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412891"
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>Cambiar un símbolo o el nombre de un símbolo (ID)

Cuando se crea un nuevo recurso u objeto de recurso, el entorno de desarrollo le asigna un nombre de símbolo predeterminado, por ejemplo, IDD_DIALOG1. Puede usar el [ventana propiedades](/visualstudio/ide/reference/properties-window) para cambiar el nombre del símbolo predeterminado o para cambiar el nombre de cualquier símbolo ya asociado a un recurso.

### <a name="to-change-a-resources-symbol-name"></a>Para cambiar el nombre del símbolo de un recurso

1. En [vista de recursos](../windows/resource-view-window.md), seleccione el recurso.

   > [!NOTE]
   > Si el proyecto no contuviera un archivo .rc, vea [Crear un nuevo archivo de script de recursos](../windows/how-to-create-a-resource-script-file.md).

2. En el **propiedades** ventana, escriba un nombre de símbolo nuevo o seleccione en la lista de símbolos existentes en el **ID** cuadro.

   Si escribe un nombre de símbolo nuevo, se le asigna automáticamente un valor.

Puede usar el [cuadro de diálogo símbolos de recursos](../windows/resource-symbols-dialog-box.md) para cambiar los nombres de los símbolos no estén asignados a un recurso. Para obtener más información, consulte [cambiar símbolos sin asignar](../windows/changing-unassigned-symbols.md).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Vea también

[Restricciones de los nombres de símbolo](../windows/symbol-name-restrictions.md)<br/>
[Identificadores de símbolo predefinidos](../windows/predefined-symbol-ids.md)