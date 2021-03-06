---
title: Comentarios en lenguaje de ensamblado | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02f4c493bac5c2a066dc0b24e2a566d49345288d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683331"
---
# <a name="assembly-language-comments"></a>Comentarios en lenguaje de ensamblado

**Específicos de Microsoft**

Las instrucciones en un bloque `__asm` pueden utilizar comentarios en lenguaje de ensamblado:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Debido a que las macros de C se expanden en una única línea lógica, evite utilizar comentarios en lenguaje de ensamblado en las macros. (Consulte [definir bloques __asm como Macros de C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Un `__asm` bloque también puede contener comentarios del estilo de C; para obtener más información, consulte [uso de C o C++ en bloques __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Uso del lenguaje de ensamblado en bloques __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>