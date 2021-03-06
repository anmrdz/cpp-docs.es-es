---
title: Requisitos de compilación para controles comunes de Windows Vista | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 969dbc59f1ae2fc90bb467bd03a02abd8d73c4f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383706"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Requisitos de compilación para los controles comunes de Windows Vista

La biblioteca Microsoft Foundation Class (MFC) es compatible con la versión 6.1 de controles comunes de Windows. Los controles comunes se incluyen en Windows Vista y la biblioteca se incluye en el SDK de Visual Studio. La biblioteca proporciona nuevos métodos que mejoran las clases existentes y las nuevas clases y métodos que admiten controles comunes de Windows Vista. Cuando se compila la aplicación, debe seguir los requisitos de compilación y la migración que se describen en las secciones siguientes.

## <a name="compilation-requirements"></a>Requisitos de compilación

### <a name="supported-versions"></a>Versiones admitidas

Algunas nuevas clases y métodos admiten sólo Windows Vista y versiones posteriores, mientras que otros métodos también admiten sistemas operativos anteriores. Una nota en la `Requirements` sección del tema de cada método especifica cuándo la mínima necesaria del sistema operativo es Windows Vista.

Incluso si el equipo no ejecuta Windows Vista, puede crear una aplicación MFC que se ejecutará en Windows Vista, si tiene los archivos de encabezado MFC versión 6.1 en el equipo. Sin embargo, controles comunes que están diseñados específicamente para Windows Vista funcionan únicamente en el sistema y son ignorados por los sistemas operativos anteriores.

### <a name="supported-character-sets"></a>Juegos de caracteres compatibles

Los nuevos controles comunes de Windows admiten solo el juego de caracteres Unicode y no el juego de caracteres ANSI. Si compila la aplicación en la línea de comandos, utilice siguientes definen ambos (/ d.) opciones del compilador para especificar Unicode como subyacente de juego de caracteres:

```
/D_UNICODE /DUNICODE
```

Si compila la aplicación en el entorno de desarrollo integrado (IDE) de Visual Studio, especifique el **juego de caracteres Unicode** opción de la **del juego de caracteres** propiedad en el **General**  nodo de las propiedades del proyecto.

La versión ANSI de varios métodos MFC han quedado en desuso a partir de versión 6.1 de controles comunes de Windows. Para obtener más información, consulte [API de ANSI en desuso](../mfc/deprecated-ansi-apis.md).

## <a name="migration-requirements"></a>Requisitos de migración

Si utiliza el IDE de Visual Studio para crear una nueva aplicación MFC que utiliza la versión 6.1 de controles comunes de Windows, el IDE declara automáticamente un manifiesto apropiado. Sin embargo, si migra una aplicación MFC existente desde una versión anterior de Visual Studio y desea usar los nuevos controles comunes, el IDE no proporciona automáticamente información de manifiesto para actualizar la aplicación. En su lugar, se debe insertar manualmente el siguiente código fuente en su **stdafx.h** archivo:

```
#ifdef UNICODE
#if defined _M_IX86
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_IA64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_X64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#else
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")
#endif
#endif
```

## <a name="see-also"></a>Vea también

[Temas generales de MFC](../mfc/general-mfc-topics.md)<br/>
[Gráfico de jerarquías](../mfc/hierarchy-chart.md)<br/>
[API ANSI en desuso](../mfc/deprecated-ansi-apis.md)

