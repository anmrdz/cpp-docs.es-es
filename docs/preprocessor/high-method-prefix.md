---
title: high_method_prefix | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fb69b9fbb7ede0ca458007aec1bee2cf38e286f
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807723"
---
# <a name="highmethodprefix"></a>high_method_prefix

**Específicos de C++**

Especifica un prefijo que se utilizará para designar propiedades y métodos de alto nivel.

## <a name="syntax"></a>Sintaxis

```
high_method_prefix("Prefix")
```

### <a name="parameters"></a>Parámetros

*Prefix*<br/>
Prefijo que se va a utilizar.

## <a name="remarks"></a>Comentarios

De forma predeterminada, las propiedades y los métodos de control de errores de alto nivel se exponen mediante funciones miembro denominadas sin prefijo. Los nombres son de la biblioteca de tipos.

**FIN de específicos de C++**

## <a name="see-also"></a>Vea también

[atributos #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[directiva #import](../preprocessor/hash-import-directive-cpp.md)