---
title: Contenedores (C++ moderno) | Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a05eada2b5828cfc654496355bddcabcafc8d60
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086153"
---
# <a name="containers-modern-c"></a>Contenedores (C++ moderno)

De forma predeterminada, utilice [vector](../standard-library/vector-class.md) como contenedor secuencial preferido en C++. Esto es equivalente a `List<T>` en lenguajes. NET.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Use [mapa](../standard-library/map-class.md) (no `unordered_map`) como contenedor asociativo predeterminado. Use [establecer](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), y [multiset](../standard-library/multiset-class.md) para casos degenerados y múltiples.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Cuando la optimización del rendimiento es necesaria, considere utilizar:

- El [matriz](../standard-library/array-class-stl.md) escriba cuando la incrustación es importante, por ejemplo, como un miembro de clase.

- Contenedores asociativos desordenados como [unordered_map](../standard-library/unordered-map-class.md). Estos tienen una sobrecarga por elemento inferior y búsqueda de tiempo constante, pero puede ser más difíciles de usar de manera correcta y eficaz.

- Ordenar `vector`. Para más información, vea [Algoritmos](../cpp/algorithms-modern-cpp.md).

No use matrices de estilo C. Para obtener información sobre las API más antiguas que necesitan acceso directo a los datos, use métodos de descriptor de acceso como `f(vec.data(), vec.size());` en su lugar.

Para obtener más información acerca de los contenedores, consulte [contenedores de biblioteca estándar de C++](../standard-library/stl-containers.md).

## <a name="see-also"></a>Vea también

[Aquí está otra vez C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Referencia del lenguaje C++](../cpp/cpp-language-reference.md)<br/>
[Biblioteca estándar de C++](../standard-library/cpp-standard-library-reference.md)