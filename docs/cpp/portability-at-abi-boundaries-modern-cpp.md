---
title: Portabilidad en los límites de ABI (C++ moderno) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 891f56d763fc86efd62fb5bae3b21498336a8ccc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058424"
---
# <a name="portability-at-abi-boundaries-modern-c"></a>Portabilidad en los límites de ABI (C++ moderno)

Usar tipos lo suficientemente portátiles y convenciones en los límites de la interfaz binaria. Un "tipo portátil" es un tipo integrado de C o un struct que contiene solo tipos integrados de C. Tipos de clase solo pueden utilizarse al llamador y destinatario de acuerdo en el diseño, una llamada a la convención, etcetera. Esto solo es posible cuando se compilan con el mismo compilador y la configuración del compilador.

## <a name="how-to-flatten-a-class-for-c-portability"></a>Cómo eliminar el formato de una clase para la portabilidad de C

Cuando los autores de llamadas puede compilarse con otro compilador/lenguaje, "aplanar" a un **extern "C"** API con una convención de llamada específica:

```cpp
// class widget {
//   widget();
//   ~widget();
//   double method( int, gadget& );
// };
extern "C" {        // functions using explicit "this"
   struct widget;   // opaque type (forward declaration only)
   widget* STDCALL widget_create();      // constructor creates new "this"
   void STDCALL widget_destroy(widget*); // destructor consumes "this"
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"
}
```

## <a name="see-also"></a>Vea también

[Aquí está otra vez C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Referencia del lenguaje C++](../cpp/cpp-language-reference.md)<br/>
[Biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)