---
title: Definir funciones insertadas de C con dllexport y dllimport | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82612d7502557c88c4abf5a974d42b3bf62c3403
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038716"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Definir funciones insertadas de C con dllexport y dllimport

**Específicos de Microsoft**

Puede definir como alineada una función con el atributo `dllexport`. En este caso, siempre se crean instancias de la función, y siempre se exporta, independientemente de si un módulo del programa hace referencia o no a la función. Se supone que otro programa importa la función.

También puede definir como alineada una función declarada con el atributo **dllimport**. En este caso, la función puede expandirse (de acuerdo con la especificación de opción del compilador /Ob (inline)), pero no puede crearse una instancia de ella. En concreto, si se toma la dirección de una función alineada importada, se devuelve la dirección de la función que reside en la DLL. Este comportamiento es el mismo que cuando se toma la dirección de una función importada no alineada.

Los datos y cadenas locales estáticos en funciones inline mantienen las mismas identidades entre la DLL y el cliente que mantendrían en un solo programa (es decir, un archivo ejecutable sin una interfaz DLL).

Tome precauciones cuando proporcione funciones insertadas importadas. Por ejemplo, si actualiza la DLL, no suponga que el cliente utilizará la versión modificada de la DLL. Para asegurarse de que se carga la versión correcta, recompile el cliente de DLL también.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Funciones de importación y exportación de archivos DLL](../c-language/dll-import-and-export-functions.md)