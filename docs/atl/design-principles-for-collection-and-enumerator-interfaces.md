---
title: Diseño de Interfaces de enumerador (ATL) y de colección | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ffe40b583a9dabeb14ce5347de6ae3d14dae724
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751490"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Principios de diseño para la recopilación y las Interfaces de enumerador

Hay diferentes principios de cada tipo de interfaz de diseño:

- Proporciona una interfaz de colección *aleatorio* el acceso a un *único* elemento de la colección a través de la `Item` método, permite a los clientes descubrir cuántos elementos se encuentran en la colección a través de la `Count` propiedad, y a menudo permite a los clientes agregar y quitar elementos.

- Proporciona una interfaz de enumerador *serie* el acceso a *varios* elementos de una colección, no permite descubrir cuántos elementos están en la colección (hasta que el enumerador deja de devolver al cliente elementos), y no proporciona ninguna manera de agregar o quitar elementos.

Cada tipo de interfaz desempeña un rol diferente al proporcionar acceso a los elementos de una colección.

## <a name="see-also"></a>Vea también

[Las colecciones y enumeradores](../atl/atl-collections-and-enumerators.md)

