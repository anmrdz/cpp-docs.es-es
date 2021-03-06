---
title: Error del compilador C2813 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8b7912edeea9edbb32632953166fc2558aeed3e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062662"
---
# <a name="compiler-error-c2813"></a>Error del compilador C2813

\#no se admite la importación con /MP

El error C2813 se genera si en un comando de compilador se especifica la opción del compilador **/MP** y dos o más archivos para compilar y uno o varios de los archivos contiene la directiva de preprocesador[#import](../../preprocessor/hash-import-directive-cpp.md) . La directiva [#import](../../preprocessor/hash-import-directive-cpp.md) genera clases de C++ a partir de los tipos de la biblioteca de tipos especificada y, a continuación, escribe las clases en dos archivos de encabezado. La directiva [#import](../../preprocessor/hash-import-directive-cpp.md) no se admite la directiva porque si varias unidades de compilación importan la misma biblioteca de tipos, las unidades entran en conflicto al intentar escribir los mismos archivos de encabezado al mismo tiempo.

Este error del compilador y el **/MP** opción del compilador son nuevas en Visual Studio 2008.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C2813. La línea de comandos del comentario "compile with:" indica al compilador que debe usar las opciones del compilador **/MP** y **/c** para compilar varios archivos. Al menos uno de los archivos contiene la directiva [#import](../../preprocessor/hash-import-directive-cpp.md) . El mismo archivo se usa dos veces para probar este ejemplo.

```
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```