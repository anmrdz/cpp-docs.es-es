---
title: Compilador advertencia (nivel 3) C4580 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90cd0b401624ea6815b31b55a7da9c8796746ce8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789207"
---
# <a name="compiler-warning-level-3-c4580"></a>Advertencia del compilador (nivel 3) C4580

[attribute] está en desuso; especifique en su lugar System::Attribute o Platform::Metadata como clase base

[[atributo](../../windows/attributes/attribute.md)] ya no es la sintaxis recomendada para crear atributos definidos por el usuario. Para obtener más información, consulte [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Para el código CLR, derive los atributos de `System::Attribute`. Para el código Windows en tiempo de ejecución, derive los atributos de `Platform::Metadata`.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se genera el error C3454 y se muestra cómo corregirlo:

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```