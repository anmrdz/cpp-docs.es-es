---
title: Asignar y liberar memoria para un BSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- bstr
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 565032ca7ddf64e93716b1c06524bd09a1a46079
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389401"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Asignación y liberación de memoria para un BSTR

Cuando creas `BSTR`s y pasarlas entre objetos COM, debe tener cuidado en el tratamiento de la memoria que utilizan con el fin de evitar pérdidas de memoria. Cuando un `BSTR` permanece dentro de una interfaz, debe liberar su memoria cuando haya terminado con él. Sin embargo, cuando un `BSTR` pasadas fuera de una interfaz, el objeto receptor responsabiliza de la administración de memoria.

En general, las reglas para asignar y liberar memoria asignan para `BSTR`s son los siguientes:

- Cuando se llama a una función que espera un `BSTR` argumento, debe asignar la memoria para el `BSTR` antes de la llamada y liberarla después. Por ejemplo:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- Cuando se llama a una función que devuelve un `BSTR`, debe liberar la cadena. Por ejemplo:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- Cuando se implementa una función que devuelve un `BSTR`, asigne la cadena pero no la libere. La recepción la función libera la memoria. Por ejemplo:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>Vea también

[Cadenas (ATL y MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)

