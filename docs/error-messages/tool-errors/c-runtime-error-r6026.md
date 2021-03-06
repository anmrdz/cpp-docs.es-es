---
title: C Runtime Error R6026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6026
dev_langs:
- C++
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5b10075912ce4fde65699cf7b2d413c0bdd10f0
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860802"
---
# <a name="c-runtime-error-r6026"></a>C Runtime Error R6026

No hay espacio suficiente para la inicialización de stdio

> [!NOTE]
> Si encuentra este mensaje de error al ejecutar una aplicación, la aplicación se cerró porque tiene un problema de memoria interna. Hay varias razones posibles para este error, pero normalmente está causado por una condición muy poca memoria. También puede deberse a un error en la aplicación, por daños en las bibliotecas de Visual C++ que utiliza o un controlador.
>
> Puede intentar seguir estos pasos para corregir este error:
>
> - Cierre otras aplicaciones en ejecución o reinicie el equipo para liberar memoria.
> - Use la **aplicaciones y características** o **programas y características** página en el **Panel de Control** para reparar o reinstalar el programa.
> - Si la aplicación funcionaba correctamente antes de una instalación reciente de otra aplicación o controlador, utilice la **aplicaciones y características** o **programas y características** página en el **Panel de Control** para quitar el nueva aplicación o el controlador e inténtelo de nuevo la aplicación.
> - Use la **aplicaciones y características** o **programas y características** página en el **Panel de Control** para reparar o reinstalar todas las copias de Microsoft Visual C++ Redistributable.
> - Comprobar **Windows Update** en el **Panel de Control** las actualizaciones de software.
> - Busque una versión actualizada de la aplicación. Si el problema persiste, póngase en contacto con el proveedor de la aplicación.

**Información para programadores**

Este error se produce cuando no hay suficiente memoria libre disponible para inicializar la compatibilidad estándar de E/S en el tiempo de ejecución de C. Este error suele producirse al iniciar la aplicación. Compruebe que la aplicación y los controladores y los archivos DLL que carga no dañar el montón durante el inicio.