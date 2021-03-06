---
title: Construir objetos de flujo de entrada | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c640f1b338fa4b0aa6dbcc408e0729fbf8ff90a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963555"
---
# <a name="constructing-input-stream-objects"></a>Construir objetos de flujo de entrada

Si solo usa el objeto `cin`, no es necesario que cree un flujo de entrada. Debe crear un flujo de entrada si usa:

- [Constructores de flujo de archivos de entrada](#vclrfinputfilestreamconstructorsanchor8)

- [Constructores de flujo de cadenas de entrada](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> Constructores de flujo de archivos de entrada

Hay dos formas de crear un flujo de archivo de entrada:

- Use la **void** constructor de argumento, a continuación, llame a la `open` función miembro:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Especifique un nombre de archivo y marcas de modo en la invocación del constructor; de esta forma, se abre el archivo durante el proceso de construcción:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> Constructores de flujo de cadenas de entrada

Los constructores de flujo de cadenas de entrada requieren la dirección del almacenamiento asignado e inicializado previamente:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Vea también

[Flujos de entrada](../standard-library/input-streams.md)<br/>
