---
title: Las herramientas del vinculador LNK1256 Error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a711343eaf64a9ef1c46a5044cb3d6a2f84c5f7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050650"
---
# <a name="linker-tools-error-lnk1256"></a>Error de las herramientas del vinculador LNK1256

Error de operación ALINK: razón

Una razón común para LNK1256 es un número de versión incorrecto para un ensamblado. El valor 65535 no está permitido en ninguna parte del número de versión del ensamblado. El intervalo válido para las versiones de ensamblado es 0 - 65534.

LNK1256 también puede producirse si ALINK no pudo encontrar el contenedor de claves nombrado. Eliminar el contenedor de claves y vuelva a agregarla a CSP de nombres seguros mediante el uso de [Sn.exe (Strong Name Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool).

Otra razón para el error LNK1256 es una discrepancia de versiones entre el vinculador y Alink.dll. Esto puede deberse a una instalación dañada de Visual Studio. Use **programas y características** en el Panel de Control de Windows para reparar o reinstalar Visual Studio.

En el siguiente ejemplo se genera el error LNK1256:

```
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```