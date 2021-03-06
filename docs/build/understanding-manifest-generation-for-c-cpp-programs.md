---
title: Descripción de la generación de manifiestos para los programas de C/C ++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91120d1c8485d43a447310440bbe0bab8f7e3b75
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726263"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>Introducción a la generación de manifiestos para los programas de C/C++

Un [manifiesto](https://msdn.microsoft.com/library/aa375365) es un documento XML que puede ser un archivo XML externo o un recurso incrustado dentro de una aplicación o un ensamblado. El manifiesto de un [aplicación aislada](/windows/desktop/SbsCs/isolated-applications) se usa para administrar los nombres y las versiones de los ensamblados en paralelo compartidos a los que se debe enlazar la aplicación en tiempo de ejecución. El manifiesto de un ensamblado en paralelo especifica sus dependencias en los nombres, versiones, recursos y otros ensamblados.

Hay dos maneras de crear un manifiesto para una aplicación aislada o un ensamblado en paralelo. En primer lugar, el autor del ensamblado puede crear manualmente un archivo de manifiesto siguiendo las reglas y requisitos de nomenclatura. Como alternativa, si un programa sólo depende de ensamblados de Visual C++ como CRT, MFC, ATL u otros, el vinculador puede generar automáticamente un manifiesto.

Los encabezados de bibliotecas de Visual C++ contienen información de ensamblado, y cuando las bibliotecas se incluyen en el código de la aplicación, se usa esta información de ensamblado por el vinculador para formar un manifiesto para el archivo binario final. El vinculador no incrusta el archivo de manifiesto dentro del archivo binario y solo puede generar el manifiesto como un archivo externo. Tener un manifiesto como un archivo externo puede no funcionar para todos los escenarios. Por ejemplo, se recomienda que los ensamblados privados tengan manifiestos incrustados. En las compilaciones de línea de comandos, como los que se utilice nmake para generar código, se puede incrustar un manifiesto con la herramienta de manifiesto; Para obtener más información, consulte [Manifest Generation en la línea de comandos](../build/manifest-generation-at-the-command-line.md). Al compilar en Visual Studio, se puede incrustar un manifiesto estableciendo una propiedad para la herramienta de manifiesto en el **las propiedades del proyecto** diálogo; vea [Manifest Generation en Visual Studio](../build/manifest-generation-in-visual-studio.md).

## <a name="see-also"></a>Vea también

[Conceptos de aplicaciones aisladas y ensamblados simultáneos](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Compilación de aplicaciones aisladas y ensamblados simultáneos de C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)