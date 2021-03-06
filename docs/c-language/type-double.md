---
title: Tipo double | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3384c801f4ed7424711b0f51a42706650b75c41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062051"
---
# <a name="type-double"></a>Tipo double

Los valores de precisión doble con tipo double tienen 8 bytes. El formato es similar al formato float, excepto que tiene un exponente 1023 que supera los 11 bits y una mantisa de 52 bits, más el bit de orden superior implícito. Este formato proporciona un intervalo de aproximadamente 1,7E–308 a 1,7E+308 para el tipo double.

**Específicos de Microsoft**

El tipo double contiene 64 bits: 1 para el signo, 11 para el exponente y 52 para la mantisa. Su intervalo es +/- 1,7E308 con al menos 15 dígitos de precisión.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Almacenamiento de tipos básicos](../c-language/storage-of-basic-types.md)