---
title: Compilación de C/C ++ de aplicaciones aisladas | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78d14f812700afa4ea0ad66b527a0e3888862f4d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716916"
---
# <a name="building-cc-isolated-applications"></a>Compilar aplicaciones aisladas de C/C++

Una aplicación aislada sólo depende de los ensamblados en paralelo y se enlaza a sus dependencias mediante un manifiesto. No es necesario para la aplicación sea totalmente aisladas para ejecutar correctamente en Windows; Sin embargo, al invertir en aislar totalmente su aplicación, puede ahorrar tiempo si necesita mantener la aplicación en el futuro. Para obtener más información sobre las ventajas de aislar totalmente su aplicación, consulte [aplicaciones aisladas](/windows/desktop/SbsCs/isolated-applications).

Cuando se compila la aplicación de C o C++ nativa con Visual C++, de forma predeterminada, Visual Studio, sistema del proyecto genera un archivo de manifiesto que describe las dependencias de la aplicación en las bibliotecas de Visual C++. Si se trata de las dependencias sola tiene la aplicación, se convertirá en una aplicación aislada en cuanto se vuelve a generar con Visual Studio. Si la aplicación utiliza otras bibliotecas en tiempo de ejecución, es posible que deba volver a generar las bibliotecas como ensamblados en paralelo siguiendo los pasos descritos en [creación de ensamblados de C o C++ por en paralelo](../build/building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Vea también

[Conceptos de aplicaciones aisladas y ensamblados simultáneos](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Compilación de aplicaciones aisladas y ensamblados simultáneos de C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)