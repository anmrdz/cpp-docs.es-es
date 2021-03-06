---
title: 'Cómo: usar un tipo nativo en una compilación de clr: | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3e56c3617b6b2a8168e35867c09858dffa84cea9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448069"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>Cómo: Utilizar un tipo nativo en una compilación con /clr

Puede definir un tipo nativo en un **/CLR** compilación y cualquier uso de ese tipo nativo desde dentro del ensamblado es válido. Sin embargo, los tipos nativos no estará disponibles para su uso de los metadatos que se hace referencia.

Cada ensamblado debe contener la definición de cada tipo nativo que se va a utilizar.

Para obtener más información, consulte [/clr (Compilación de Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Ejemplo

Este ejemplo crea un componente que define y utiliza un tipo nativo.

```
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

## <a name="example"></a>Ejemplo

Este ejemplo define a un cliente que utiliza el componente. Tenga en cuenta que es un error al tener acceso al tipo nativo, a menos que se define en la operación de compilación.

```
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>Vea también

[Usar la interoperabilidad de C++ (PInvoke implícito)](../dotnet/using-cpp-interop-implicit-pinvoke.md)