---
title: Conversiones estándar y conversión Boxing implícita | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, implicit
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 393554a43a647ef7582ef4a6c4d29ed11061d0c9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379039"
---
# <a name="standard-conversions-and-implicit-boxing"></a>Conversiones estándar y conversión boxing implícita

El compilador elegirá una conversión estándar a través de una conversión que requiere la conversión boxing.

## <a name="example"></a>Ejemplo

```
// clr_implicit_boxing_Std_conversion.cpp
// compile with: /clr
int f3(int ^ i) {   // requires boxing
   return 1;
}

int f3(char c) {   // no boxing required, standard conversion
   return 2;
}

int main() {
   int i = 5;
   System::Console::WriteLine(f3(i));
}
```

```Output
2
```

## <a name="see-also"></a>Vea también

[Conversión boxing](../windows/boxing-cpp-component-extensions.md)