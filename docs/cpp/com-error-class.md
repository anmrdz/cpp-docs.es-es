---
title: _com_error (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfbaf1f0c88eaeb71bc4dfbbf2dca72c8d07251e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117444"
---
# <a name="comerror-class"></a>_com_error (Clase)

**Específicos de Microsoft**

Un **_com_error** objeto representa una condición de excepción detectada por las funciones de contenedor de control de errores en los archivos de encabezado generados a partir de la biblioteca de tipos o por una de las clases de compatibilidad con COM. El **_com_error** clase encapsula el código de error HRESULT y asociada ninguna `IErrorInfo Interface` objeto.

### <a name="construction"></a>Construcción

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|Construye un **_com_error** objeto.|

### <a name="operators"></a>Operadores

|||
|-|-|
|[operador =](../cpp/com-error-operator-equal.md)|Asigna una existente **_com_error** objeto a otro.|

### <a name="extractor-functions"></a>Funciones de extractor

|||
|-|-|
|[Error](../cpp/com-error-error.md)|Recupera el valor HRESULT pasado al constructor.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Recupera el objeto `IErrorInfo` pasado al constructor.|
|[WCode](../cpp/com-error-wcode.md)|Recupera el código de error de 16 bits asignado en el valor de HRESULT encapsulado.|

### <a name="ierrorinfo-functions"></a>Funciones de IErrorInfo

|||
|-|-|
|[Descripción](../cpp/com-error-description.md)|Llama a la función `IErrorInfo::GetDescription`.|
|[HelpContext](../cpp/com-error-helpcontext.md)|Llama a la función `IErrorInfo::GetHelpContext`.|
|[HelpFile](../cpp/com-error-helpfile.md)|Llama a la función `IErrorInfo::GetHelpFile`.|
|[Source](../cpp/com-error-source.md)|Llama a la función `IErrorInfo::GetSource`.|
|[GUID](../cpp/com-error-guid.md)|Llama a la función `IErrorInfo::GetGUID`.|

### <a name="format-message-extractor"></a>Extractor de mensajes de formato

|||
|-|-|
|[Mensaje de error](../cpp/com-error-errormessage.md)|Recupera el mensaje de cadena para HRESULT almacenado en el **_com_error** objeto.|

### <a name="exepinfowcode-to-hresult-mappers"></a>Asignadores de ExepInfo.wCode a HRESULT

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Asigna el valor HRESULT de 32 bits a 16 bits `wCode`.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Mapas de bits de 16 `wCode` HRESULT de 32 bits.|

**FIN de Específicos de Microsoft**

## <a name="requirements"></a>Requisitos

**Encabezado:** \<comdef.h >

`Lib:` omsuppw.lib o comsuppwd.lib (vea [/Zc: wchar_t (wchar_t es tipo nativo)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) para obtener más información)

## <a name="see-also"></a>Vea también

[Clases de compatibilidad con COM del compilador](../cpp/compiler-com-support-classes.md)<br/>
[Interfaz IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)