---
title: Error del compilador C3227 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3227
dev_langs:
- C++
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ddf2ec945a8bdbe103631d8346641e1370eda216
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096631"
---
# <a name="compiler-error-c3227"></a>Error del compilador C3227

'parámetro': no se puede usar 'keyword' para asignar un tipo genérico

Para crear una instancia de un tipo, se requiere un constructor adecuado. Sin embargo, el compilador no es capaz de garantizar que esté disponible un constructor adecuado.

Puede usar las plantillas en lugar de los genéricos para resolver este error, o puede usar varios métodos para crear una instancia del tipo.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera C3227.

```
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```