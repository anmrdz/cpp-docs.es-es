---
title: Error del compilador C3459 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3459
dev_langs:
- C++
helpviewer_keywords:
- C3459
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abde90828cac4f45685b7a21b50705474aedde72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026795"
---
# <a name="compiler-error-c3459"></a>Error del compilador C3459

'attribute': el atributo solamente se permite en el indizador de clase (propiedad indexada predeterminada)

Un atributo que se ha diseñado para aplicarse a una propiedad de indizador de clase se usó de forma incorrecta.

Para obtener más información, consulte [Cómo: utilizar propiedades en C++ / c++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C3459.

```
// C3459.cpp
// compile with: /clr /c
public ref class MyString {
public:
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459
   property int Prop;
};

// OK
public ref class MyString2 {
   array<int>^ MyArr;
public:
   MyString2() {
      MyArr = gcnew array<int>(5);
   }

   [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK
   property int default[int] {
      int get(int index) {
         return MyArr[index];
      }
      void set(int index, int value) {
         MyArr[index] = value;
      }
   }
};
```