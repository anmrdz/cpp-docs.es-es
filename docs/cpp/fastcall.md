---
title: __fastcall | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fastcall_cpp
- __fastcall
- _fastcall
dev_langs:
- C++
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa181349ab01ea2a375bacbb5e23d073a99f3f11
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161247"
---
# <a name="fastcall"></a>__fastcall

**Específicos de Microsoft**

El **__fastcall** convención de llamada especifica que los argumentos para funciones deben pasarse en registros, siempre que sea posible. Esta convención de llamada solo se aplica a la arquitectura x86. En la lista siguiente se muestra la implementación de esta convención de llamada.

|Elemento|Implementación|
|-------------|--------------------|
|Orden de paso de argumento|Los primeros dos argumentos DWORD o menores que se encuentran en la lista de argumentos de izquierda a derecha se pasan en registros ECX y EDX; el resto de los argumentos se pasan en la pila de derecha a izquierda.|
|Responsabilidad de mantenimiento de pila|Al llamar a la función aparece el argumento de la pila.|
|Convención de creación de nombres representativos|Arroba (\@) se antepone a los nombres; una arroba seguido del número de bytes (en formato decimal) en el parámetro tiene el sufijo lista a los nombres.|
|Convención de traducción de mayúsculas y minúsculas|No se lleva a cabo una traducción de mayúsculas y minúsculas.|

> [!NOTE]
>  Las futuras versiones del compilador pueden utilizar distintos registros para almacenar parámetros.

Mediante el [/GR](../build/reference/gd-gr-gv-gz-calling-convention.md) opción del compilador hace que cada función del módulo compile como **__fastcall** a menos que la función se declara con un atributo en conflicto, o el nombre de la función `main` .

El **__fastcall** palabra clave acepta y omite los compiladores que tienen como destino ARM y x64 arquitecturas; en un x64 chip, por convención, los cuatro primeros argumentos se pasan en registros cuando sea posible y se pasan argumentos adicionales en la pila. Para obtener más información, consulte [general de x64 convenciones de llamada](../build/overview-of-x64-calling-conventions.md). En un chip ARM, se puede pasar hasta cuatro argumentos enteros y ocho argumentos de punto flotante en los registros; los argumentos adicionales se pasan en la pila.

En el caso de funciones de clase no estáticas, si la función se define fuera de línea, no es necesario especificar el modificador de convención de llamada en la definición fuera de línea. Es decir, para los métodos miembro no estáticos de clase, en el momento de la definición se supone la convención de llamada especificada durante la declaración. Dada esta definición de clase:

```cpp
struct CMyClass {
   void __fastcall mymethod();
};
```

esto:

```cpp
void CMyClass::mymethod() { return; }
```

equivale a esto:

```cpp
void __fastcall CMyClass::mymethod() { return; }
```

Para ofrecer compatibilidad con versiones anteriores, **_fastcall** es un sinónimo de **__fastcall** a menos que la opción de compilador [/Za \(deshabilitar extensiones de lenguaje)](../build/reference/za-ze-disable-language-extensions.md) es especificado.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo, se pasan argumentos a la función `DeleteAggrWrapper` en los registros:

```cpp
// Example of the __fastcall keyword
#define FASTCALL    __fastcall

void FASTCALL DeleteAggrWrapper(void* pWrapper);
// Example of the __ fastcall keyword on function pointer
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Paso de argumentos y convenciones de nomenclatura](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Palabras clave](../cpp/keywords-cpp.md)