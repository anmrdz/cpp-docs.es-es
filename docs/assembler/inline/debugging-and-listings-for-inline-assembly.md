---
title: Depuración y listas para el ensamblado insertado | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6cca954ae15252b97d883ba8491fdb98e506f68
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689294"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Depuración y listas para el ensamblado insertado

**Específicos de Microsoft**

Se pueden depurar programas que contienen código ensamblador en línea con un depurador de nivel de origen si se compila con la [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) opción.

En el depurador, puede establecer puntos de interrupción en las líneas de C o C++ y de lenguaje de ensamblado. Si habilita el modo de ensamblado mixto y de origen, puede mostrar la forma de origen y desensamblada del código de ensamblado.

Tenga en cuenta que la inclusión de varias instrucciones de ensamblado o del lenguaje de origen en una línea pueden dificultar la depuración. En modo de origen, puede utilizar el depurador para establecer puntos de interrupción en una línea, pero no en instrucciones individuales en la misma línea. El mismo principio se aplica a un bloque `__asm` definido como una macro de C, que se expande en una sola línea lógica.

Si crea un origen mixto y un ensamblado con el [/FAS](../../build/reference/fa-fa-listing-file.md) opción del compilador, la lista contiene el origen y el ensamblado de formularios de cada línea del lenguaje de ensamblado. Las macros no se expanden en listados, sino durante la compilación.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Uso del lenguaje de ensamblado en bloques __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>