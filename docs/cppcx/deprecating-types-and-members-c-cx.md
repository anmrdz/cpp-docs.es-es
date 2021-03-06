---
title: Dejar en desuso tipos y miembros (C++ / c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 500b93f3a84ecb39706b5c1575887a7339d1fdd4
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102096"
---
# <a name="deprecating-types-and-members-ccx"></a>Dejar en desuso tipos y miembros (C++/CX)

En C / c++ / CX, degradación de tipos en tiempo de ejecución de Windows y miembros para los productores y consumidores con el [en desuso](/uwp/api/windows.foundation.metadata.deprecatedattribute) se admite el atributo. Si utilizas una API a la que se ha aplicado este atributo, obtienes un mensaje de advertencia en tiempo de compilación que indica que la API está desusada y que te recomienda una API alternativa. Puedes aplicar este atributo en tus propios tipos y métodos públicos, así como proporcionar tus propios mensajes personalizados.

> [!CAUTION]
> El [en desuso](/uwp/api/windows.foundation.metadata.deprecatedattribute) atributo es para uso exclusivo con tipos de Windows en tiempo de ejecución. Para las clases de C++ estándar y miembros, use [__declspec (deprecated)](../cpp/deprecated-cpp.md).

### <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo marcar como desusadas tus propias API públicas, por ejemplo, en un componente de Windows en tiempo de ejecución. El segundo parámetro de tipo [Windows: Foundation:: Metadata:: deprecationtype](/uwp/api/windows.foundation.metadata.deprecationtype) especifica si se va la API obsoletas o eliminadas. Actualmente, solo se admite el valor DeprecationType::Deprecated. El tercer parámetro en el atributo especifica el [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) al que se aplica el atributo.

```

namespace wfm = Windows::Foundation::Metadata;

public ref class Bicycle sealed
{

public:
    property double Speed;

    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]
    double ComputeAngularVelocity();
};
```

## <a name="supported-targets"></a>Destinos admitidos

En la tabla siguiente se enumeran las construcciones a las que se puede aplicar el atributo Deprecated:

||
|-|
|Control XAML|
|delegado|
|evento|
|campo de enumeración|
|enum|
|struct|
|método|
|clase|
|interfaz|
|propiedad|
|campo de struct|
|constructor parametrizado|

## <a name="see-also"></a>Vea también

[Sistema de tipos](../cppcx/type-system-c-cx.md)<br/>
[Referencia del lenguaje de Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Referencia de espacios de nombres](../cppcx/namespaces-reference-c-cx.md)