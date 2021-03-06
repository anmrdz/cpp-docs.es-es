---
title: Error del compilador C2078 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2078
dev_langs:
- C++
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8de17341bfb1ad5031be04e977ab68ae4ed1bcb5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111516"
---
# <a name="compiler-error-c2078"></a>Error del compilador C2078

hay demasiados inicializadores

El número de inicializadores supera el número de objetos que deben inicializarse.

El compilador puede deducir la asignación correcta de inicializadores a objetos y objetos internos cuando se eliden las llaves internas de la lista de inicializadores. Si se usan todas las llaves, se elimina la ambigüedad y, como resultado, se consigue una asignación correcta. Si las llaves se usan de forma parcial, puede generarse el error C2078 debido a la ambigüedad en la asignación de los inicializadores a los objetos.

El ejemplo siguiente genera el error C2078 y muestra cómo corregirlo:

```
// C2078.cpp
// Compile by using: cl /c /W4 C2078.cpp
struct S {
   struct {
      int x, y;
   } z[2];
};

int main() {
   int d[2] = {1, 2, 3};   // C2078
   int e[2] = {1, 2};      // OK

   char a[] = {"a", "b"};  // C2078
   char *b[] = {"a", "b"}; // OK
   char c[] = {'a', 'b'};  // OK

   S s1{1, 2, 3, 4};       // OK
   S s2{{1, 2}, {3, 4}};   // C2078
   S s3{{1, 2, 3, 4}};     // OK
   S s4{{{1, 2}, {3, 4}}}; // OK
}

```