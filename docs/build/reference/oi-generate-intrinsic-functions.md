---
title: -Oi (generar funciones intrínsecas) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs:
- C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 792d1e1bc0ea2f6044bc9ad145d30c1fda3e3648
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423876"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (Generar funciones intrínsecas)

Reemplaza algunas llamadas función con formas intrínsecas o especiales de la función que ayudará a la aplicación se ejecute más rápido.

## <a name="syntax"></a>Sintaxis

```
/Oi[-]
```

## <a name="remarks"></a>Comentarios

Programas que usan funciones intrínsecas son más rápidas porque no tiene la sobrecarga de llamadas de función, pero podría ser más grandes debido al código adicional que se creó.

Consulte [intrínseco](../../preprocessor/intrinsic.md) para obtener más información en el que las funciones tienen formas intrínsecas.

**/Oi** es solo una solicitud al compilador para reemplazar algunas llamadas de función con formas intrínsecas; el compilador puede llamar a la función (y no reemplazar la llamada de función con una función intrínseca) si dará como resultado un mejor rendimiento.

**x86 específico**

Las funciones intrínsecas de punto flotante no se realiza ninguna comprobación especial en los valores de entrada y por lo que funcionan en intervalos de entrada restringidos y tener control de excepciones diferentes y las condiciones de límite que las rutinas de biblioteca con el mismo nombre. El uso de las formas intrínsecas auténticas implica la pérdida de control de excepciones de IEEE y de `_matherr` y `errno` funcionalidad; esta última implica la pérdida de conformidad con ANSI. Sin embargo, las formas intrínsecas pueden acelerar considerablemente los programas que usan punto flotante, y muchos programas, los problemas de conformidad tienen poco valor práctico.

Puede usar el [Za](../../build/reference/za-ze-disable-language-extensions.md) opción del compilador para reemplazar la generación de opciones verdaderas intrínsecas de punto flotante. En este caso, las funciones se generan como rutinas de biblioteca que pasan los argumentos directamente al chip de punto flotante, en lugar de insertarlos en la pila del programa.

**END x86 específico**

También usa [intrínseco](../../preprocessor/intrinsic.md) para crear funciones intrínsecas o [(función) (C/C ++)](../../preprocessor/function-c-cpp.md) para forzar explícitamente una llamada de función.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Haga clic en la carpeta **C/C++** .

1. Haga clic en el **optimización** página de propiedades.

1. Modificar el **habilitar funciones intrínsecas** propiedad.

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

- Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.

## <a name="see-also"></a>Vea también

[/O (Opciones) (Optimizar código)](../../build/reference/o-options-optimize-code.md)<br/>
[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)<br/>
[Intrínsecos del controlador](../../intrinsics/compiler-intrinsics.md)