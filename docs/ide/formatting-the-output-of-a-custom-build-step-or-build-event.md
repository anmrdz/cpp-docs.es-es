---
title: Dar formato a la presentación de un paso de compilación personalizada o un evento de compilación | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a975951142c028ffcfb8ece870ab3ac2d2b60fc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203254"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Dar formato a la presentación de un paso de compilación personalizada o un evento de compilación

Si el resultado de un paso de compilación personalizada o un evento de compilación tiene el formato correcto, los usuarios obtendrán las ventajas siguientes:

- Los errores y las advertencias se enumeran en la ventana **Salida**.

- La salida aparece en la ventana **Lista de tareas**.

- Al hacer clic en la salida en la ventana **Salida** se muestra el tema correspondiente.

- Las operaciones con F1 están habilitadas en las ventanas **Lista de tareas** o **Salida**.

El formato de la salida debe ser el siguiente:

> {<em>filename</em>**(**<em>line#</em> \[**,** <em>column#</em>]**)** &#124; *toolname*} **:** \[ <em>any text</em> ] {**error** &#124; **warning**} <em>code+number</em>**:**<em>localizable string</em> \[ <em>any text</em> ]

Dónde:

- {*a* &#124; *b*} es la elección de *a* o *b*.

- \[<em>item</em>] es un parámetro o una cadena opcional.

- **Bold** representa un literal.

Por ejemplo:

> C:\\*archivo_de_origen.cpp*(134) : error C2143: error de sintaxis : falta ";" delante de "}"

> LINK: error irrecuperable LNK1104: no se puede abrir el archivo "*una_biblioteca.lib*"

## <a name="see-also"></a>Vea también

[Descripción de los pasos de compilación personalizada y los eventos de compilación](../ide/understanding-custom-build-steps-and-build-events.md)