---
title: '/ Zc: trigraphs (sustitución de trígrafos) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce8c9d13fa062ddac0f31eac0e20fba1266c7a8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707738"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Sustitución de trígrafos)

Cuando **/Zc: trigraphs** se especifica, el compilador reemplaza una secuencia de caracteres de trígrafo mediante el uso de un carácter de puntuación correspondiente.

## <a name="syntax"></a>Sintaxis

> **/ Zc: trigraphs**[**-**]

## <a name="remarks"></a>Comentarios

Un *trígrafo* consta de dos signos de interrogación consecutivos ("??") seguido de un tercer carácter único. El estándar del lenguaje C admite trígrafos para archivos de origen que usen un juego de caracteres que no contenga representaciones gráficas adecuadas para algunos caracteres de puntuación. Por ejemplo, cuando se habilitan los trígrafos, el compilador reemplaza el "?? = "trígrafo mediante el carácter '#'. A través de C ++ 14, se admiten trígrafos como en C. El estándar C ++ 17 quita trígrafos del lenguaje C++. En el código de C++, el **/Zc: trigraphs** opción del compilador habilita la sustitución de secuencias de trígrafos por el carácter de puntuación correspondiente. **/Zc:trigraphs-** deshabilita la sustitución de trígrafos.

El **/Zc: trigraphs** opción está desactivada de forma predeterminada, y la opción no está afectado cuando el [/ permissive-](permissive-standards-conformance.md) se especifica la opción.

Para obtener una lista de los trígrafos C o C++ y un ejemplo que muestra cómo usar trígrafos, consulte [trígrafos](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, vea [Trabajar con propiedades del proyecto](../../ide/working-with-project-properties.md).

1. Seleccione el **propiedades de configuración** > **C o C++** > **línea de comandos** página de propiedades.

1. Modificar el **opciones adicionales** propiedad incluir **/Zc: trigraphs** o **/Zc:trigraphs-** y, a continuación, elija **Aceptar**.

## <a name="see-also"></a>Vea también

[/Zc (Ajuste)](../../build/reference/zc-conformance.md)<br/>
[Trígrafos](../../c-language/trigraphs.md)<br/>
