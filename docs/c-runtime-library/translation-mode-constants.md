---
title: Constantes de modo de traducción | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
dev_langs:
- C++
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c2eff59c8f766b96c1abaeaa2eb9b369720cc75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46015956"
---
# <a name="translation-mode-constants"></a>Constantes del modo de traducción

## <a name="syntax"></a>Sintaxis

```

#include <fcntl.h>

```

## <a name="remarks"></a>Comentarios

Las constantes del manifiesto `_O_BINARY` y `_O_TEXT` determinan el modo de traducción de archivos (`_open` y `_sopen`) o el modo de traducción de secuencias (`_setmode`).

Los valores permitidos son:

|||
|-|-|
`_O_TEXT`  | Abre un archivo en modo de texto (traducido). Las combinaciones de retorno de carro y avance de línea (CR-LF) se traducen en un único carácter de avance de línea (LF) en la entrada. Los caracteres de salto de línea se traducen en combinaciones CR-LF en la salida. Además, CTRL+Z se interpreta como carácter de final de archivo en la entrada. En los archivos abiertos para lectura y lectura y escritura, `fopen` comprueba si existe un CTRL+Z al final del archivo y lo quita, si es posible. Se hace así porque el uso de las funciones `fseek` y `ftell` para desplazarse por un archivo que finaliza con CTRL+Z puede hacer que `fseek` se comporte de manera incorrecta cerca del final del archivo.
`_O_BINARY`  | Abre un archivo en modo binario (sin traducir). Las traducciones anteriores se suprimen.
`_O_RAW`  | Igual a `_O_BINARY`. Admite la compatibilidad con C 2.0.

Para obtener más información, vea [E/S de archivo en modo texto y en modo binario](../c-runtime-library/text-and-binary-mode-file-i-o.md) y [Constantes de traducción de archivo](../c-runtime-library/file-translation-constants.md).

## <a name="see-also"></a>Vea también

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_pipe](../c-runtime-library/reference/pipe.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_setmode](../c-runtime-library/reference/setmode.md)<br/>
[Constantes globales](../c-runtime-library/global-constants.md)