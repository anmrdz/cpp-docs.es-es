---
title: Delegate (clase) | Documentos de Microsoft
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Delegate
dev_langs: C++
helpviewer_keywords: Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: d7bdd03cef8aab0344cf3fa72ef40341c11287d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="platformdelegate-class"></a>Platform::Delegate (Clase)
Representa un objeto de función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
public delegate void delegate_name();  
```  
  
### <a name="members"></a>Miembros  
 La clase Delegate tiene los métodos Equals(), GetHashCode() y ToString() que se derivan de [Platform::Object Class](../cppcx/platform-object-class.md).  
  
### <a name="remarks"></a>Comentarios  
 Use la palabra clave [delegate](../windows/delegate-cpp-component-extensions.md) para crear delegados; no use Platform::Delegate de manera explícita. Para obtener más información, vea [Delegados (Guía de programación de C#)](../cppcx/delegates-c-cx.md). Para un ejemplo de cómo crear y usar un delegado, vea [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
### <a name="requirements"></a>Requisitos  
 **Cliente mínimo admitido:** Windows 8  
  
 **Servidor mínimo admitido:** Windows Server 2012  
  
 **Espacio de nombres:** Platform  
  
 **Metadatos:** platform.winmd  
  
## <a name="see-also"></a>Vea también  
 [Espacio de nombres de plataforma](../cppcx/platform-namespace-c-cx.md)