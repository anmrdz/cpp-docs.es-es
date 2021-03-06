---
title: Clases ref de plantilla (C++ / c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd720c2bdcc9bd0baab2606e473858450508feff
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107179"
---
# <a name="template-ref-classes-ccx"></a>Clases ref de plantilla (C++/CX)

Las plantillas de C++ no se publican para metadatos y, por consiguiente, no pueden tener accesibilidad pública ni protegida en tu programa. Puedes, por supuesto, utilizar las plantillas de C++ estándar internamente en tu programa. Además, puedes definir una clase ref privada como plantilla y puedes declarar una clase ref de plantilla especializada de forma explícita como miembro privado de una clase ref pública.

## <a name="authoring-ref-class-templates"></a>Crear plantillas de clase ref

En el ejemplo siguiente se muestra cómo declarar una clase ref privada como plantilla y también cómo declarar una plantilla de C++ estándar, y cómo declarar ambas como miembros de una clase ref pública. Tenga en cuenta que se puede especializar la plantilla estándar de C++ mediante un tipo en tiempo de ejecución de Windows, en este caso un Platform:: String ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Vea también

[Sistema de tipos (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Referencia del lenguaje de Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Referencia de espacios de nombres](../cppcx/namespaces-reference-c-cx.md)