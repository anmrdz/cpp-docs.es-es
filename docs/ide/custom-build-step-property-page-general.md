---
title: 'Paso de compilación personalizada (Página de propiedades): General | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f34628ddd11c8cefdd00553f779a22448c2ec99d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404805"
---
# <a name="custom-build-step-property-page-general"></a>Paso de compilación personalizada (Página de propiedades): General

Para cada combinación de configuración y plataforma de destino del proyecto, puede especificar un paso personalizado que se realizará cuando se compile el proyecto.

Para la versión de Linux de esta página, vea [Propiedades de paso de compilación personalizada (C++ para Linux)](../linux/prop-pages/custom-build-step-linux.md).

## <a name="uielement-list"></a>Lista de UIElement

- **Línea de comandos**

   Comando que va a ejecutar el paso de compilación personalizada.

- **Descripción**

   Mensaje que se muestra cuando se ejecuta el paso de compilación personalizada.

- **Salidas**

   Archivo de salida que genera el paso de compilación personalizada. Este valor es necesario para que las compilaciones incrementales funcionen correctamente.

- **Dependencias adicionales**

   Lista delimitada por puntos y coma de los archivos de entrada adicionales que se usarán para el paso de compilación personalizada.

- **Ejecutar después y Ejecutar antes**

   Estas opciones definen cuándo se ejecuta el paso de compilación personalizada en el proceso de compilación, en relación con los destinos enumerados. Los destinos más frecuentes son BuildGenerateSources, BuildCompile y BuildLink, ya que representan los pasos principales del proceso de compilación. Otros destinos frecuentes son Midl, CLCompile y Link.

- **Tratar salida como contenido**

   Esta opción solo es significativa para las aplicaciones de la Plataforma universal de Windows o de Windows Phone, que incluyen todos los archivos de contenido en el paquete .appx.

### <a name="to-specify-a-custom-build-step"></a>Para especificar un paso de compilación personalizada

1. En la barra de menús, seleccione **Proyecto**, **Propiedades**. Para obtener más información, vea [Trabajar con propiedades de proyecto](../ide/working-with-project-properties.md).

1. En el cuadro de diálogo **Páginas de propiedades**, navegue hasta la página **Propiedades de configuración**, **Paso de compilación personalizada**, **General**.

1. Modifique la configuración.

## <a name="see-also"></a>Vea también

[Páginas de propiedades](../ide/property-pages-visual-cpp.md)