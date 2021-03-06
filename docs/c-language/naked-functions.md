---
title: Naked (Funciones) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked functions
- functions [C++], naked
- prolog code
- epilog code
ms.assetid: 2543c8af-00d4-4a2a-8a87-e746da1f9929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 134584ed1acd502ecbf74fe755850761df8c08e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061492"
---
# <a name="naked-functions"></a>Naked (Funciones)

**Específicos de Microsoft**

El atributo de clase de almacenamiento `naked` es una extensión específica de Microsoft para el lenguaje C. Para las funciones declaradas con el atributo de clase de almacenamiento `naked`, el compilador genera código sin código de prólogo y epílogo. Puede utilizar esta característica para escribir sus propias secuencias de código de prólogo/epílogo mediante código del ensamblador alineado. Las funciones naked son especialmente útiles al escribir controladores de dispositivos virtuales.

Dado que el atributo `naked` solo es pertinente a la definición de una función y no es un modificador de tipo, las funciones naked utilizan la sintaxis de atributo extendido, descrita en [Atributos extendidos de clase de almacenamiento](../c-language/c-extended-storage-class-attributes.md).

En el ejemplo siguiente se define una función con el atributo `naked`:

```
__declspec( naked ) int func( formal_parameters )
{
   /* Function body */
}
```

O bien, alternativamente:

```
#define Naked   __declspec( naked )

Naked int func( formal_parameters )
{
   /* Function body */
}
```

El atributo `naked` solo afecta a la naturaleza de la generación de código del compilador para las secuencias de prólogo y epílogo de la función. No afecta al código que se genera para llamar a esas funciones. Por tanto, el atributo `naked` no se considera parte del tipo de la función y los punteros a función no pueden tener el atributo `naked`. Además, el atributo `naked` no se puede aplicar a una definición de datos. Por ejemplo, el siguiente código genera errores:

```
__declspec( naked ) int i;  /* Error--naked attribute not */
                            /* permitted on data declarations. */
```

El atributo `naked` solo es pertinente para la definición de la función y no se puede especificar en el prototipo de la función. La siguiente declaración genera un error de compilación:

```
__declspec( naked ) int func();   /* Error--naked attribute not */
                     /* permitted on function declarations.    */   \
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Definiciones de función de C](../c-language/c-function-definitions.md)