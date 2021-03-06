---
title: Función de devolución de llamada (WRL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
dev_langs:
- C++
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f3bce2db1ed3a418347d8a8b0a53cb6958fb63e0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063177"
---
# <a name="callback-function-wrl"></a>Función de devolución de llamada (WRL)

Crea un objeto cuya función de miembro es un método de devolución de llamada.

## <a name="syntax"></a>Sintaxis

```cpp
template<
   typename TDelegateInterface,
   typename TCallback
>
ComPtr<TDelegateInterface> Callback(
   TCallbackcallback
);
template<
   typename TDelegateInterface,
   typename TCallbackObject
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)()
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8,
   TArg9)
);
```

### <a name="parameters"></a>Parámetros

*TDelegateInterface*<br/>
Un parámetro de plantilla que especifica la interfaz del delegado al que se llamará cuando se produzca un evento.

*TCallback*<br/>
Un parámetro de plantilla que especifica el tipo de un objeto que representa un objeto y su función miembro de devolución de llamada.

*TCallbackObject*<br/>
Un parámetro de plantilla que especifica el objeto cuya función miembro es el método al que se debe llamar cuando se produce un evento.

*TArg1*<br/>
Un parámetro de plantilla que especifica el tipo del primer argumento del método de devolución de llamada.

*TArg2*<br/>
Un parámetro de plantilla que especifica el tipo del segundo argumento del método de devolución de llamada.

*TArg3*<br/>
Un parámetro de plantilla que especifica el tipo del tercer argumento del método de devolución de llamada.

*TArg4*<br/>
Un parámetro de plantilla que especifica el tipo del cuarto argumento del método de devolución de llamada.

*TArg5*<br/>
Un parámetro de plantilla que especifica el tipo del quinto argumento del método de devolución de llamada.

*TArg6*<br/>
Un parámetro de plantilla que especifica el tipo del sexto argumento del método de devolución de llamada.

*TArg7*<br/>
Un parámetro de plantilla que especifica el tipo del séptimo argumento del método de devolución de llamada.

*TArg8*<br/>
Un parámetro de plantilla que especifica el tipo del octavo argumento del método de devolución de llamada.

*TArg9*<br/>
Un parámetro de plantilla que especifica el tipo del noveno argumento del método de devolución de llamada.

*devolución de llamada*<br/>
Un objeto que representa el objeto de devolución de llamada y su función miembro.

*object*<br/>
El objeto a cuya función miembro se llama cuando se produce un evento.

*Método*<br/>
La función miembro a la que se llamará cuando se produzca un evento.

## <a name="return-value"></a>Valor devuelto

Un objeto cuya función miembro es el método de devolución de llamada especificado.

## <a name="remarks"></a>Comentarios

La base de un objeto delegado debe ser `IUnknown`, no `IInspectable`.

## <a name="requirements"></a>Requisitos

**Encabezado:** event.h

**Espacio de nombres:** Microsoft::WRL

## <a name="see-also"></a>Vea también

[Microsoft::WRL (espacio de nombres)](../windows/microsoft-wrl-namespace.md)