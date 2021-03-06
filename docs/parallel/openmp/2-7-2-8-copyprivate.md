---
title: 2.7.2.8 copyprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6815afe12344f94ed33d6b9260472f3e29eb72a0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406365"
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

El **copyprivate** cláusula proporciona un mecanismo para usar una variable privada para difundir un valor de un miembro de un equipo a los demás miembros. Es una alternativa al uso de una variable compartida para el valor al que proporciona este tipo de variable compartida puede ser difícil (por ejemplo, en una necesidad de una variable diferente en cada nivel de recursividad). El **copyprivate** cláusula solamente puede aparecer en el **único** directiva.

La sintaxis de la **copyprivate** cláusula es como sigue:

```

copyprivate(
variable-list
)

```

El efecto de la **copyprivate** cláusula en una de las variables en su lista de variables que se produce después de la ejecución del bloque estructurado asociado con el **único** construir y antes de cualquiera de los subprocesos en la equipo han dejado la barrera al final de la construcción. A continuación, en todos los demás subprocesos en el equipo de cada variable en el *lista de variables*, esa variable queda definida (como si de asignación) con el valor de la correspondiente estructurado de variable en el subproceso que ejecutó la construcción bloque.

Restricciones para el **copyprivate** cláusula son los siguientes:

- Una variable que se especifica en el **copyprivate** cláusula no debe aparecer en un **privada** o **firstprivate** cláusula para el mismo **único**directiva.

- Si un **único** la directiva con un **copyprivate** cláusula se encuentra en la extensión dinámica de una región paralela, todas las variables que se especifica en el **copyprivate** cláusula debe de forma privada en el contexto envolvente.

- Una variable que se especifica en el **copyprivate** cláusula debe tener un operador de asignación de copia no ambigua accesible.