---
title: Ventajas del carácter de portabilidad de los juegos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d016b95ea2a2d5d94b8db47a2d6c9d5cc577083f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064451"
---
# <a name="benefits-of-character-set-portability"></a>Ventajas de la portabilidad de los juegos de caracteres

Puede beneficiarse del uso de las características de portabilidad de tiempo de ejecución de C y MFC incluso aunque no piense actualmente internacionalizar su aplicación:

- Código portable hace que el código base flexible. Más adelante se puede mover fácilmente a Unicode o MBCS.

- El uso de Unicode hace que las aplicaciones para Windows más eficaz. Dado que Windows utiliza Unicode, se deben traducir cadenas no Unicode que se pasan a y desde el sistema operativo que incurre en sobrecarga.

## <a name="see-also"></a>Vea también

[Unicode y MBCS](../text/unicode-and-mbcs.md)<br/>
[Compatibilidad con Unicode](../text/support-for-unicode.md)