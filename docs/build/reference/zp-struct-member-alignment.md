---
title: -Zp (alineación de miembros de Struct) | Microsoft Docs
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0268f5c5d5d34d8fa244dc6260889bea6b1e837a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715915"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Alineación de miembros de estructura)

Controla cómo se empaquetan los miembros de una estructura en memoria y especifica el mismo tipo de empaquetado para todas las estructuras de un módulo.

## <a name="syntax"></a>Sintaxis

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Comentarios

Al especificar el **/Zp**_n_ opción, cada miembro de la estructura detrás del primero se almacena en el tamaño del tipo del miembro o *n*-límites de bytes (donde *n* es 1, 2, 4, 8 o 16), lo que sea menor.

Los valores de empaquetado disponibles se describen en la tabla siguiente:

|/Zp argumento|Efecto|
|-|-|
|1|Empaqueta las estructuras en límites de 1 byte. Igual que **/Zp**.|
|2|Empaqueta las estructuras en límites de 2 bytes.|
|4|Empaqueta las estructuras en límites de 4 bytes.|
|8|Empaqueta las estructuras en límites de 8 bytes (valor predeterminado).|
|16| Empaqueta las estructuras en límites de 16 bytes.|

No debe utilizar esta opción a menos que tenga requisitos específicos de alineación.

> [!WARNING]
> Encabezados de C++ en el SDK de Windows se suponen **/zp8** de empaquetado. Memoria pueden dañarse si la **/Zp** se cambia la configuración al usar los encabezados del SDK de Windows.

También puede usar [pack](../../preprocessor/pack.md) empaquetado de estructura de control. Para obtener más información sobre la alineación, vea:

- [align](../../cpp/align-cpp.md)

- [__alignof (Operador)](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Ejemplos de alineación de estructuras](../../build/examples-of-structure-alignment.md) (x64 específico)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Seleccione el **C o C++** > **generación de código** página de propiedades.

1. Modificar el **alineación de miembros de Struct** propiedad.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Vea también

- [Opciones del compilador](../../build/reference/compiler-options.md)
- [Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)
