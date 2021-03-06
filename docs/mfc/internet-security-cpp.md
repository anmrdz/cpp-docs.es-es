---
title: Seguridad de Internet (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b61df9a17903f50ea922edf9c29eee926063254
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055416"
---
# <a name="internet-security-c"></a>Seguridad de Internet (C++)

Seguridad de código es un problema importante para los desarrolladores y usuarios de aplicaciones de Internet. Existen riesgos: código malintencionado, el código que se ha alterado y código desde sitios desconocidos o autores.

Hay dos enfoques básicos para la seguridad al desarrollar para Internet. El primero se denomina "espacio aislado". En este enfoque, una aplicación está restringida a un determinado conjunto de API y excluirse peligrosos, como E/S de archivos donde un programa podría destruir los datos en el equipo del usuario. El segundo se implementa mediante las firmas digitales. Este enfoque se conoce como "shrinkwrap" para Internet. Código se comprueba y firma con la tecnología de claves pública/clave privada. Antes de ejecuta el código, la firma digital se comprueba para asegurarse de que el código procede de un origen autenticado conocido, y que el código no se ha modificado desde que se ha firmado.

En el primer caso, confiar en que la aplicación no hará ningún daño y confía en el origen de la aplicación. En el segundo, las firmas digitales se usan para comprobar la autenticidad. La firma digital es un estándar del sector que se usa para identificar y proporcionar detalles sobre el publicador del código. Su tecnología se basa en estándares, incluidos RSA y X.509. Los exploradores suelen permiten a los usuarios elegir si desean descargar y ejecutar código de origen desconocido.

## <a name="see-also"></a>Vea también

[Tareas de programación para Internet de MFC](../mfc/mfc-internet-programming-tasks.md)<br/>
[Fundamentos de programación para Internet de MFC](../mfc/mfc-internet-programming-basics.md)

