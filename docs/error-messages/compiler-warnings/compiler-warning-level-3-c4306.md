---
title: Compilador advertencia (nivel 3) C4306 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4306
dev_langs:
- C++
helpviewer_keywords:
- C4306
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab5372213819375a6c1fec3cfc43970415b6486a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219999"
---
# <a name="compiler-warning-level-3-c4306"></a>Advertencia del compilador (nivel 3) C4306

> '*identificador*': conversión de '*type1*'para'*type2*' de mayor tamaño

El identificador es de tipo en un puntero de mayor tamaño. Los bits superiores sin relleno del nuevo tipo será rellenan con ceros.

Esta advertencia puede indicar una conversión no deseada. El puntero resultante puede no ser válido.