---
title: PTR::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::com::ptr::Attach
- ptr::Attach
- ptr.Attach
- msclr.com.ptr.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: 81d930de-cb2a-4c30-9bd6-94d65942c47a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 873a36e69c767a6101173f545520e60bfa6ce598
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315345"
---
# <a name="ptrattach"></a>ptr::Attach

Adjunta un objeto COM para un `com::ptr`.

## <a name="syntax"></a>Sintaxis

```
void Attach(
   _interface_type * _right
);
```

#### <a name="parameters"></a>Parámetros

*a la _derecha*<br/>
El puntero de interfaz COM para adjuntar.

## <a name="exceptions"></a>Excepciones

Si el `com::ptr` ya posee una referencia a un objeto COM, `Attach` produce <xref:System.InvalidOperationException>.

## <a name="remarks"></a>Comentarios

Una llamada a `Attach` hace referencia al objeto COM pero no libera la referencia del llamador.

Pasar `NULL` a `Attach` da como resultado que se va a realizar ninguna acción.

## <a name="example"></a>Ejemplo

En este ejemplo implementa una clase CLR que utiliza un `com::ptr` para ajustar su miembro privado `IXMLDOMDocument` objeto. El `ReplaceDocument` llama primero a la función de miembro `Release` en cualquier anteriormente pertenecían a objeto y, a continuación, llama a `Attach` para adjuntar un nuevo objeto de documento.

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="requirements"></a>Requisitos

**Archivo de encabezado** \<msclr\\com\\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Vea también

[ptr (Miembros)](../dotnet/ptr-members.md)<br/>
[ptr::operator=](../dotnet/ptr-operator-assign.md)<br/>
[ptr::Release](../dotnet/ptr-release.md)