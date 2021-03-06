---
title: MAPI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2ca182da3a0300604415b790c0aba138c8fd7a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439112"
---
# <a name="mapi"></a>MAPI

En este artículo se describe la interfaz de programación de aplicaciones de mensajería de Microsoft (MAPI) para desarrolladores de aplicaciones de mensaje de cliente. MFC proporciona compatibilidad con un subconjunto de MAPI en clase `CDocument` pero no encapsula toda la API. Para obtener más información, consulte [compatibilidad MAPI en MFC](../mfc/mapi-support-in-mfc.md).

MAPI es un conjunto de funciones que usan aplicaciones basadas en correo electrónico y habilitados para correo electrónico para crear, manipular, transferir y almacenar mensajes de correo. Ofrece las herramientas para definir el propósito y el contenido de los mensajes de correo electrónico de los desarrolladores de aplicaciones y proporciona flexibilidad para administrar los mensajes almacenados. MAPI también proporciona una interfaz común que los desarrolladores de aplicaciones pueden usar para crear habilitados para correo electrónico y aplicaciones basadas en el correo electrónico independientes del sistema de mensajería subyacente.

Los clientes de mensajería proporcionan una interfaz de usuario para la interacción con el sistema de mensajería de Windows (WMS) de Microsoft. Esta interacción suele incluir solicitar los servicios de proveedores compatibles con MAPI, como almacenes de mensajes y libretas de direcciones.

Para obtener más información acerca de MAPI, vea los artículos en la Guía de Win32 de mensajería (MAPI) del SDK de Windows.

## <a name="in-this-section"></a>En esta sección

[Compatibilidad MAPI en MFC](../mfc/mapi-support-in-mfc.md)

## <a name="see-also"></a>Vea también

[CDocument:: OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument:: OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

