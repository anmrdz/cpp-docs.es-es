---
title: '&lt;remarks&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- remarks
- <remarks>
dev_langs:
- C++
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 732904e854a5f5ce05513fd302f1398a7c6ce28d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374574"
---
# <a name="ltremarksgt-visual-c"></a>&lt;remarks&gt; (Visual C++)

La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](../ide/summary-visual-cpp.md). Esta información se muestra en la ventana [Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code) y en el informe web de comentario de código.

## <a name="syntax"></a>Sintaxis

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>Parámetros

*description*<br/>
Descripción del miembro.

## <a name="remarks"></a>Comentarios

Compile con [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) para procesar los comentarios de documentación a un archivo.

## <a name="example"></a>Ejemplo

```
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>Vea también

[Documentación de XML](../ide/xml-documentation-visual-cpp.md)