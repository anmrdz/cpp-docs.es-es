---
title: Error del compilador C3142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3142
dev_langs:
- C++
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8a4e049c4e2846a011b60b50159e07982e3b747
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041628"
---
# <a name="compiler-error-c3142"></a>Error del compilador C3142

'property_name': no puede tomar la dirección de una propiedad

La dirección de una propiedad no está disponible para el desarrollador.

El ejemplo siguiente genera el error C3142:

```
// C3142_2.cpp
// compile with: /clr
using namespace System;
ref class CSize {
private:
   property int Size {
      int get();
   }
};

int main() {
    &CSize::Size; // C3142
}
```
