---
title: Implementación de ClickOnce para aplicaciones de Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fabce61d84072cd27482f94fa32c8fd91850b797
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378909"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Implementación de ClickOnce para aplicaciones de Visual C++

Visual Studio proporciona dos tecnologías diferentes para implementar aplicaciones Windows: implementación de ClickOnce o implementación de [Windows Installer](/windows/desktop/Msi/windows-installer-portal).

## <a name="clickonce-deployment-in-c"></a>Implementación de ClickOnce en C++

El entorno de desarrollo de Visual C++ no admite directamente la implementación de proyectos de Visual C++ con ClickOnce, pero existen herramientas que pueden usarlo.

> [!NOTE]
>  Visual Studio es compatible con ClickOnce en los entornos de desarrollo de Visual C# y Visual Basic. Si el proyecto de Visual C++ es una dependencia de un proyecto de Visual C#, puede publicar la aplicación (incluidas sus dependencias) mediante la implementación de ClickOnce desde el entorno de desarrollo de Visual C#.

Para implementar una aplicación de Visual C++ con ClickOnce, primero tiene que generar un [manifiesto de aplicación ClickOnce](/visualstudio/deployment/clickonce-application-manifest) y un [manifiesto de implementación de ClickOnce](/visualstudio/deployment/clickonce-deployment-manifest) mediante [Mage.exe (Herramienta de generación y edición de manifiestos)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) o su versión de interfaz gráfica de usuario (para obtener información, vea [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

Utilice primero Mage.exe para compilar el manifiesto de aplicación; el archivo resultante tendrá la extensión .manifest. A continuación, utilice Mage.exe para compilar el manifiesto de implementación; el archivo resultante tendrá la extensión .application. Por último, firme los manifiestos.

El manifiesto de aplicación debe especificar el procesador de destino (**x86**, **x64** o **ARM**). Vea [Implementación de requisitos previos para las aplicaciones de 64 bits](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) para obtener información sobre estas opciones.

A su vez, el nombre de la aplicación y de los manifiestos de implementación debe ser diferente del nombre de la aplicación de C++. Esto evita el conflicto entre el manifiesto de aplicación creado por Mage.exe y el manifiesto externo que forma parte de la aplicación de C++.

La implementación necesitará la instalación de las bibliotecas de Visual C++ de las que dependa la aplicación. Para determinar las dependencias de una aplicación determinada, puede utilizar depends.exe o la utilidad DUMPBIN con la opción /DEPENDENTS. Para obtener más información sobre las dependencias, vea [Descripción de las dependencias de una aplicación de Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Es posible que tenga que ejecutar VCRedist.exe; esta utilidad instala las bibliotecas de Visual C++ en el equipo de destino.

También puede que tenga que compilar un programa previo (instalador de requisitos previos) para que la aplicación implemente los componentes de requisito previo; para obtener información sobre el programa previo, vea [Crear paquetes de arranque](/visualstudio/deployment/creating-bootstrapper-packages).

Para obtener una descripción más detallada de la tecnología, vea [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Para obtener un ejemplo detallado de implementación de ClickOnce, vea [Tutorial: Implementar manualmente una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Vea también

[Mage.exe (Herramienta de generación y edición de manifiestos)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (Herramienta de creación de certificados)](https://msdn.microsoft.com/library/windows/desktop/aa386968)<br>
[Implementar aplicaciones de escritorio](../ide/deploying-native-desktop-applications-visual-cpp.md)<br>
[Implementar aplicaciones, servicios y componentes](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Crear paquetes de arranque](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[Programación de .NET con C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Interoperabilidad nativa y de .NET](../dotnet/native-and-dotnet-interoperability.md)