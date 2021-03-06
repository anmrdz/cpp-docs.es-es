---
title: _com_error::ErrorMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afe11d570658ee077e8fdffe925349731f1921fd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111373"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage

**Específicos de Microsoft**

Recupera el mensaje de cadena para HRESULT almacenado en el objeto `_com_error`.

## <a name="syntax"></a>Sintaxis

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Valor devuelto

Devuelve el mensaje de cadena para HRESULT grabado dentro del `_com_error` objeto. Si el valor de HRESULT es un 16 bits asignado [wCode](../cpp/com-error-wcode.md), a continuación, un mensaje genérico "`IDispatch error #<wCode>`" se devuelve. Si no se encuentra ningún mensaje, se devuelve un mensaje genérico “`Unknown error #<hresult>`”. La cadena devuelta es Unicode o cadena multibyte, dependiendo del estado de la macro _UNICODE.

## <a name="remarks"></a>Comentarios

Recupera el texto del mensaje del sistema adecuado para HRESULT grabado dentro del `_com_error` objeto. El texto del mensaje del sistema se obtiene mediante una llamada a Win32 [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) función. La API `FormatMessage` asigna la cadena devuelta, que se libera cuando se destruye el objeto `_com_error`.

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[_com_error (Clase)](../cpp/com-error-class.md)