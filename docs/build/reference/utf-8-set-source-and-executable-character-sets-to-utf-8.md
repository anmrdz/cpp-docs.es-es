---
title: -utf-8 (establecer origen y ejecutable juegos a UTF-8 de caracteres) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 218ea7986e37ce9cfa98aeeb1da3c209bef73f8f
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029689"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/ UTF-8 (establecer origen y el ejecutable juegos de caracteres en UTF-8)

Especifica el origen juego de caracteres y los caracteres de ejecución establecido como UTF-8.

## <a name="syntax"></a>Sintaxis

```
/utf-8
```

## <a name="remarks"></a>Comentarios

Puede usar el **/UTF-8** opción para especificar caracteres de origen y de ejecución se establece como codificados con UTF-8. Equivale a especificar **/source-charset:utf-/execution 8-charset:utf-8** en la línea de comandos. Cualquiera de estas opciones también habilita la **/Validate/CharSet** opción predeterminada. Para obtener una lista de admite identificadores de páginas de código y juego de caracteres de nombres, vea [identificadores de páginas de código](/windows/desktop/Intl/code-page-identifiers).

De forma predeterminada, Visual Studio detecta una marca de orden de bytes para determinar si el archivo de origen está en un formato codificado de Unicode, por ejemplo, UTF-16 o UTF-8. Si no se encuentra ninguna marca de orden de bytes, se supone que el archivo de origen se codifica utilizando la página de códigos del usuario actual, a menos que haya especificado una página de códigos mediante **/UTF-8** o **/Source-CharSet** opción. Visual Studio le permite guardar el código fuente de C++ mediante cualquiera de las varias codificaciones de caracteres. Para obtener información acerca de los juegos de caracteres de origen y ejecución, consulte [juegos de caracteres](../../cpp/character-sets.md) en la documentación del lenguaje.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades de proyecto](../../ide/working-with-project-properties.md).

1. Expanda el **propiedades de configuración**, **C o C++**, **línea de comandos** carpeta.

1. En **opciones avanzadas**, agregue el **/UTF-8** opción y especifique la codificación preferida.

1. Elija **Aceptar** para guardar los cambios.

## <a name="see-also"></a>Vea también

[Opciones del compilador](../../build/reference/compiler-options.md)<br/>
[Establecer las opciones del compilador](../../build/reference/setting-compiler-options.md)<br/>
[/ Execution-CharSet (establecer juego de caracteres de ejecución)](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source/charset (Establecer el juego de caracteres de origen)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/validate/charset (Validar los caracteres compatibles)](../../build/reference/validate-charset-validate-for-compatible-characters.md)