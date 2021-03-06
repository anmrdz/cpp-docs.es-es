---
title: Con la etiqueta instrucciones | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fd0850c12adeb6d45298445f8f739978591b133
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072113"
---
# <a name="labeled-statements"></a>Instrucciones con etiqueta

Las etiquetas se usan para transferir el control de programas directamente a la instrucción especificada.

```
identifier :  statement
case constant-expression :  statement
default :  statement
```

El ámbito de una etiqueta es toda la función donde se declara.

## <a name="remarks"></a>Comentarios

Hay tres tipos de instrucciones con etiquetas. En todas ellas se utiliza el carácter de dos puntos para distinguir el tipo de etiqueta de la instrucción. La etiqueta case y las etiquetas predeterminadas son específicas para las instrucciones case.

```cpp
#include <iostream>
using namespace std;

void test_label(int x) {

    if (x == 1){
        goto label1;
    }
    goto label2;

label1:
    cout << "in label1" << endl;
    return;

label2:
    cout << "in label2" << endl;
    return;
}

int main() {
    test_label(1);  // in label1
    test_label(2);  // in label2
}
```

**La instrucción goto**

La apariencia de un *identificador* etiqueta en el programa de origen declara una etiqueta. Solo un [goto](../cpp/goto-statement-cpp.md) instrucción puede transferir el control a un *identificador* etiqueta. El fragmento de código siguiente muestra el uso de la **goto** instrucción y un *identificador* etiqueta:

Una etiqueta no puede aparecer por sí misma; debe estar asociada siempre a una instrucción. Si se necesita la propia etiqueta, coloque una instrucción null detrás de la etiqueta.

La etiqueta tiene ámbito de función y no se puede volver a declarar dentro de la función. Sin embargo, se puede utilizar el mismo nombre como una etiqueta en diferentes funciones.

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
}

//Output: At Test2 label.
```

**La instrucción case**

Las etiquetas que aparecen después de la **caso** palabra clave no puede aparecer también fuera un **cambiar** instrucción. (Esta restricción también se aplica a la **predeterminada** palabra clave.) El fragmento de código siguiente muestra el uso correcto de **caso** etiquetas:

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );
      EndPaint( hWnd, &ps );
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-case-statement"></a>Etiquetas en la instrucción case

Las etiquetas que aparecen después de la **caso** palabra clave no puede aparecer también fuera un **cambiar** instrucción. (Esta restricción también se aplica a la **predeterminada** palabra clave.) El fragmento de código siguiente muestra el uso correcto de **caso** etiquetas:

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      // Obtain a handle to the device context.
      // BeginPaint will send WM_ERASEBKGND if appropriate.

      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );

      // Inform Windows that painting is complete.

      EndPaint( hWnd, &ps );
      break;

   case WM_CLOSE:
      // Close this window and all child windows.

      KillTimer( hWnd, TIMER1 );
      DestroyWindow( hWnd );
      if ( hWnd == hWndMain )
         PostQuitMessage( 0 );  // Quit the application.
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-goto-statement"></a>Etiquetas en la instrucción goto

La apariencia de un *identificador* etiqueta en el programa de origen declara una etiqueta. Solo un [goto](../cpp/goto-statement-cpp.md) instrucción puede transferir el control a un *identificador* etiqueta. El fragmento de código siguiente muestra el uso de la **goto** instrucción y un *identificador* etiqueta:

Una etiqueta no puede aparecer por sí misma; debe estar asociada siempre a una instrucción. Si se necesita la propia etiqueta, coloque una instrucción null detrás de la etiqueta.

La etiqueta tiene ámbito de función y no se puede volver a declarar dentro de la función. Sin embargo, se puede utilizar el mismo nombre como una etiqueta en diferentes funciones.

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
// At Test2 label.
}
```

## <a name="see-also"></a>Vea también

[Información general sobre las instrucciones de C++](../cpp/overview-of-cpp-statements.md)<br/>
[switch (Instrucción) (C++)](../cpp/switch-statement-cpp.md)