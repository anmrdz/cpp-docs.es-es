---
title: Clases genéricas (C++ / c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5d87663402081a06270f09547b2d61477d5ea3f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056911"
---
# <a name="generic-classes-ccli"></a>Clases genéricas (C++/CLI)

Se declara una clase genérica con el formato siguiente:

## <a name="syntax"></a>Sintaxis

```cpp
[attributes]
generic <class-key type-parameter-identifier(s)>
[constraint-clauses]
[accessibility-modifiers] ref class identifier  [modifiers]
[: base-list]
{
class-body
} [declarators] [;]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, se utilizan los términos siguientes:

*Atributos*<br/>
(Opcional) Información declarativa adicional. Para obtener más información sobre los atributos y clases de atributos, vea atributos.

*clave de clase*<br/>
Cualquier **clase** o **typename**

*tipo de-parámetro-identificadores*, lista separada por comas de identificadores que especifican los nombres de los parámetros de tipo.

*cláusulas de restricción*<br/>
Una lista (no separados por comas) de **donde** cláusulas especifica las restricciones para los parámetros de tipo. Toma la forma:

> **donde** *identificador de parámetro de tipo* **:** *lista de restricciones***...**

*lista de restricciones*<br/>
*clase o interfaz*[`,` *...* ]

*modificadores de accesibilidad*<br/>
Modificadores de accesibilidad para la clase genérica. Para el tiempo de ejecución de Windows, es el único modificador permitido **privada**. Para common language runtime, los modificadores permitidos son **privada** y **pública**.

*identifier*<br/>
El nombre de la clase genérica, cualquier identificador de C++ válido.

*Modificadores*<br/>
(Opcional) Permite incluyen los modificadores **sealed** y **abstracta**.

*base-list*<br/>
Una lista que contiene la clase base y las interfaces implementadas, todas separadas por comas.

*cuerpo de la clase*<br/>
El cuerpo de la clase, que contiene los campos, las funciones miembro, etcetera.

*declaradores*<br/>
Declaraciones de las variables de este tipo. Por ejemplo: `^` *identificador*[`,` ...]

Puede declarar clases genéricas, como los siguientes (tenga en cuenta que la palabra clave **clase** puede usarse en lugar de **typename**). En este ejemplo, `ItemType`, `KeyType` y `ValueType` son tipos desconocidos especificados en el punto donde el tipo. `HashTable<int, int>` es un tipo del tipo genérico construido `HashTable<KeyType, ValueType>`. Un número de diferentes tipos construidos puede construirse a partir un tipo genérico único. Construido a partir de las clases genéricas de tipos construidos se tratan como cualquier otro tipo de clase ref.

```cpp
// generic_classes_1.cpp
// compile with: /clr
using namespace System;
generic <typename ItemType>
ref struct Stack {
   // ItemType may be used as a type here
   void Add(ItemType item) {}
};

generic <typename KeyType, typename ValueType>
ref class HashTable {};

// The keyword class may be used instead of typename:
generic <class ListItem>
ref class List {};

int main() {
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();
}
```

Ambos tipos de valor (ya sea integrados como tipos **int** o **doble**, o tipos de valor definido por el usuario) y tipos de referencia pueden usarse como un argumento de tipo genérico. La sintaxis dentro de la definición genérica es el mismo, independientemente. Sintácticamente, el tipo desconocido se trata como si fuera un tipo de referencia. Sin embargo, el tiempo de ejecución es capaz de determinar, si el tipo utilizado en realidad es un tipo de valor y sustituya el código generado adecuado para el acceso directo a los miembros. Tipos de valor utilizados como argumentos de tipo genérico no se han convertido y por lo tanto, no sufren la disminución del rendimiento asociada con la conversión boxing. La sintaxis utilizada dentro del cuerpo de la clase genérica debe ser `T^` y `->` en lugar de `.`. Cualquier uso de [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) para el tipo de parámetro se adecuadamente interpretará el tiempo de ejecución como la creación de un tipo de valor simple si el argumento de tipo es un tipo de valor.

También puede declarar una clase genérica con [restricciones en parámetros de tipo genérico (C++ / c++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) en los tipos que se pueden usar para el parámetro de tipo. En el ejemplo siguiente se utiliza para cualquier tipo `ItemType` debe implementar la `IItem` interfaz. Al intentar utilizar **int**, por ejemplo, que no implementa `IItem`, se generará un error en tiempo de compilación porque el argumento de tipo no satisface la restricción.

```cpp
// generic_classes_2.cpp
// compile with: /clr /c
interface class IItem {};
generic <class ItemType>
where ItemType : IItem
ref class Stack {};
```

Las clases genéricas en el mismo espacio de nombres no se puede sobrecargar cambiando solo el número o los tipos de parámetros de tipo. Sin embargo, si cada clase reside en un espacio de nombres diferente, se pueden sobrecargar. Por ejemplo, considere las siguientes dos clases, `MyClass` y `MyClass<ItemType>`, en los espacios de nombres `A` y `B`. A continuación, se pueden sobrecargar las dos clases en un espacio de nombres tercer C:

```cpp
// generic_classes_3.cpp
// compile with: /clr /c
namespace A {
   ref class MyClass {};
}

namespace B {
   generic <typename ItemType>
   ref class MyClass2 { };
}

namespace C {
   using namespace A;
   using namespace B;

   ref class Test {
      static void F() {
         MyClass^ m1 = gcnew MyClass();   // OK
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK
      }
   };
}
```

La clase base y las interfaces base no pueden ser parámetros de tipo. Sin embargo, la clase base puede incluir el parámetro de tipo como argumento, como en el caso siguiente:

```cpp
// generic_classes_4.cpp
// compile with: /clr /c
generic <typename ItemType>
interface class IInterface {};

generic <typename ItemType>
ref class MyClass : IInterface<ItemType> {};
```

Los constructores y destructores se ejecutan una vez para cada instancia de objeto (como de costumbre); los constructores estáticos se ejecutan una vez para cada tipo construido.

## <a name="fields-in-generic-classes"></a>Campos en clases genéricas

En esta sección se muestra el uso de la instancia y los campos estáticos en clases genéricas.

### <a name="instance-variables"></a>Variables de instancia

Variables de instancia de una clase genérica pueden tener tipos y los inicializadores de variables que incluyan parámetros de tipo de la clase envolvente.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, tres instancias diferentes de la clase genérica, MyClass\<ItemType >, se crean utilizando los argumentos de tipo adecuado (**int**, **doble**y **cadena**).

```cpp
// generics_instance_fields1.cpp
// compile with: /clr
// Instance fields on generic classes
using namespace System;

generic <typename ItemType>
ref class MyClass {
// Field of the type ItemType:
public :
   ItemType field1;
   // Constructor using a parameter of the type ItemType:
   MyClass(ItemType p) {
   field1 = p;
   }
};

int main() {
   // Instantiate an instance with an integer field:
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);
   Console::WriteLine("Integer field = {0}", myObj1->field1);

   // Instantiate an instance with a double field:
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);
   Console::WriteLine("Double field = {0}", myObj2->field1);

   // Instantiate an instance with a String field:
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");
   Console::WriteLine("String field = {0}", myObj3->field1);
   }
```

```Output
Integer field = 123
Double field = 1.23
String field = ABC
```

## <a name="static-variables"></a>Variables estáticas

En la creación de un nuevo tipo genérico, se crean nuevas instancias de cualquier variable estática y se ejecuta cualquier constructor estático para ese tipo.

Las variables estáticas pueden usar los parámetros de tipo de la clase envolvente.

## <a name="example"></a>Ejemplo

El ejemplo siguiente se muestra cómo utilizar los campos estáticos y un constructor estático dentro de una clase genérica.

```cpp
// generics_static2.cpp
// compile with: /clr
using namespace System;

interface class ILog {
   void Write(String^ s);
};

ref class DateTimeLog : ILog {
public:
   virtual void Write(String^ s) {
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);
   }
};

ref class PlainLog : ILog {
public:
   virtual void Write(String^ s) { Console::WriteLine(s); }
};

generic <typename LogType>
where LogType : ILog
ref class G {
   static LogType s_log;

public:
   G(){}
   void SetLog(LogType log) { s_log = log; }
   void F() { s_log->Write("Test1"); }
   static G() { Console::WriteLine("Static constructor called."); }
};

int main() {
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();
   g1->SetLog(gcnew PlainLog());
   g1->F();

   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();
   g2->SetLog(gcnew DateTimeLog());

   // prints date
   // g2->F();
}
```

```Output
Static constructor called.
Static constructor called.
Static constructor called.
Test1
```

## <a name="methods-in-generic-classes"></a>Métodos en clases genéricas

Los métodos en clases genéricas pueden ser genéricos a sí mismos; métodos genéricos no se parametrizarán implícitamente por el parámetro de tipo de clase.

Las siguientes reglas especiales se aplican a métodos en clases genéricas:

- Métodos en clases genéricas pueden usar parámetros de tipo como parámetros, tipos de valor devuelto o variables locales.

- Métodos en clases genéricas pueden usar tipos construidos abiertos o cerrados como parámetros, tipos de valor devuelto o variables locales.

### <a name="non-generic-methods-in-generic-classes"></a>Métodos no genéricos en clases genéricas

Los métodos en clases genéricas que no tienen ningún parámetro de tipo adicional normalmente se conocen como no genérico aunque la clase genérica envolvente implícitamente los parámetros.

La firma de un método genérico no puede incluir uno o más parámetros de tipo de la clase envolvente, ya sea directamente o en un tipo construido abierto. Por ejemplo:

`void MyMethod(MyClass<ItemType> x) {}`

El cuerpo de estos métodos también puede usar estos parámetros de tipo.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara un método no genérico, `ProtectData`, dentro de una clase genérica, `MyClass<ItemType>`. El método usa el parámetro de tipo de clase `ItemType` en la firma en un tipo construido abierto.

```cpp
// generics_non_generic_methods1.cpp
// compile with: /clr
// Non-generic methods within a generic class.
using namespace System;

generic <typename ItemType>
ref class MyClass {
public:
   String^ name;
   ItemType data;

   MyClass(ItemType x) {
      data = x;
   }

   // Non-generic method using the type parameter:
   virtual void ProtectData(MyClass<ItemType>^ x) {
      data = x->data;
   }
};

// ItemType defined as String^
ref class MyMainClass: MyClass<String^> {
public:
   // Passing "123.00" to the constructor:
   MyMainClass(): MyClass<String^>("123.00") {
      name = "Jeff Smith";
   }

   virtual void ProtectData(MyClass<String^>^ x) override {
      x->data = String::Format("${0}**", x->data);
   }

   static void Main() {
      MyMainClass^ x1 = gcnew MyMainClass();

      x1->ProtectData(x1);
      Console::WriteLine("Name: {0}", x1->name);
      Console::WriteLine("Amount: {0}", x1->data);
   }
};

int main() {
   MyMainClass::Main();
}
```

```Output
Name: Jeff Smith
Amount: $123.00**
```

## <a name="generic-methods-in-generic-classes"></a>Métodos genéricos en clases genéricas

Puede declarar métodos genéricos en clases genéricos y no genéricos. Por ejemplo:

## <a name="example"></a>Ejemplo

```cpp
// generics_method2.cpp
// compile with: /clr /c
generic <typename Type1>
ref class G {
public:
   // Generic method having a type parameter
   // from the class, Type1, and its own type
   // parameter, Type2
   generic <typename Type2>
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }

   // Non-generic method:
   // Can use the class type param, Type1, but not Type2.
   void Method2(Type1 t1) { F(t1, t1); }

   void F(Object^ o1, Object^ o2) {}
};
```

El método no genérico es continúa siendo genérico en el sentido de que se parametrice mediante el parámetro de tipo de la clase, pero no tiene ningún parámetro de tipo adicionales.

Todos los tipos de métodos en clases genéricas pueden ser estático genérico, incluido, instancia y métodos virtuales.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra la declaración y uso de métodos genéricos dentro de las clases genéricas:

```cpp
// generics_generic_method2.cpp
// compile with: /clr
using namespace System;
generic <class ItemType>
ref class MyClass {
public:
   // Declare a generic method member.
   generic <class Type1>
   String^ MyMethod(ItemType item, Type1 t) {
      return String::Concat(item->ToString(), t->ToString());
   }
};

int main() {
   // Create instances using different types.
   MyClass<int>^ myObj1 = gcnew MyClass<int>();
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();

   // Calling MyMethod using two integers.
   Console::WriteLine("MyMethod returned: {0}",
            myObj1->MyMethod<int>(1, 2));

   // Calling MyMethod using an integer and a string.
   Console::WriteLine("MyMethod returned: {0}",
            myObj2->MyMethod<int>("Hello #", 1));

   // Calling MyMethod using two strings.
   Console::WriteLine("MyMethod returned: {0}",
       myObj3->MyMethod<String^>("Hello ", "World!"));

   // generic methods can be called without specifying type arguments
   myObj1->MyMethod<int>(1, 2);
   myObj2->MyMethod<int>("Hello #", 1);
   myObj3->MyMethod<String^>("Hello ", "World!");
}
```

```Output
MyMethod returned: 12
MyMethod returned: Hello #1
MyMethod returned: Hello World!
```

## <a name="using-nested-types-in-generic-classes"></a>Uso de los tipos anidados en clases genéricas

Al igual que con las clases normales, puede declarar otros tipos dentro de una clase genérica. La declaración de clase anidada es parametrizar implícitamente mediante los parámetros de tipo de la declaración de clase externa. Por lo tanto, se define una clase anidada distinta para cada tipo construido externa. Por ejemplo, en la declaración,

```cpp
// generic_classes_5.cpp
// compile with: /clr /c
generic <typename ItemType>
ref struct Outer {
   ref class Inner {};
};
```

El tipo `Outer<int>::Inner` no es igual al tipo `Outer<double>::Inner`.

Al igual que con los métodos genéricos en clases genéricas, se pueden definir parámetros de tipo adicionales para el tipo anidado. Si usa los mismos nombres de parámetro de tipo en la clase interna y externa, el parámetro de tipo interno oculta el parámetro de tipo externo.

```cpp
// generic_classes_6.cpp
// compile with: /clr /c
generic <typename ItemType>
ref class Outer {
   ItemType outer_item;   // refers to outer ItemType

   generic <typename ItemType>
   ref class Inner {
      ItemType inner_item;   // refers to Inner ItemType
   };
};
```

Dado que no hay ninguna manera de hacer referencia al parámetro de tipo externo, el compilador generará una advertencia en esta situación.

Cuando se denominan construidos tipos genéricos anidados, el parámetro de tipo para el tipo externo no se incluye en la lista de parámetros de tipo para el tipo interno, aunque el tipo interno se parametriza implícitamente por el parámetro de tipo del tipo externo. En el caso anterior, sería un nombre de un tipo construido `Outer<int>::Inner<string>`.

El ejemplo siguiente muestra la creación y lectura de una lista vinculada de uso de los tipos anidados en clases genéricas.

## <a name="example"></a>Ejemplo

```cpp
// generics_linked_list.cpp
// compile with: /clr
using namespace System;
generic <class ItemType>
ref class LinkedList {
// The node class:
public:
   ref class Node {
   // The link field:
   public:
      Node^ next;
      // The data field:
      ItemType item;
   } ^first, ^current;
};

ref class ListBuilder {
public:
   void BuildIt(LinkedList<double>^ list) {
      /* Build the list */
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};
      Console::WriteLine("Building the list:");

      for (int n=0; n<=4; n++) {
         // Create a new node:
         list->current = gcnew LinkedList<double>::Node();

         // Assign a value to the data field:
         list->current->item = m[n];

         // Set the link field "next" to be the same as
         // the "first" field:
         list->current->next = list->first;

         // Redirect "first" to the new node:
         list->first = list->current;

         // Display node's data as it builds:
         Console::WriteLine(list->current->item);
      }
   }

   void ReadIt(LinkedList<double>^ list) {
      // Read the list
      // Make "first" the "current" link field:
      list->current = list->first;
      Console::WriteLine("Reading nodes:");

      // Read nodes until current == null:
      while (list->current != nullptr) {
         // Display the node's data field:
         Console::WriteLine(list->current->item);

         // Move to the next node:
         list->current = list->current->next;
      }
   }
};

int main() {
   // Create a list:
   LinkedList<double>^ aList = gcnew LinkedList<double>();

   // Initialize first node:
   aList->first = nullptr;

   // Instantiate the class, build, and read the list:
   ListBuilder^ myListBuilder = gcnew ListBuilder();
   myListBuilder->BuildIt(aList);
   myListBuilder->ReadIt(aList);
}
```

```Output
Building the list:
0.1
0.2
0.3
0.4
0.5
Reading nodes:
0.5
0.4
0.3
0.2
0.1
```

## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>Propiedades, eventos, indizadores y operadores en clases genéricas

- Propiedades, eventos, indizadores y operadores que pueden usar los parámetros de tipo de la clase contenedora genérica como valores devueltos, parámetros o variables locales, como cuando `ItemType` es un parámetro de tipo de una clase:

    ```cpp
    public ItemType MyProperty {}
    ```

- Propiedades, eventos, indizadores y los operadores no sí se puede parametrizar.

## <a name="example"></a>Ejemplo

En este ejemplo se muestra declaraciones de una propiedad de instancia dentro de una clase genérica.

```cpp
// generics_generic_properties1.cpp
// compile with: /clr
using namespace System;

generic <typename ItemType>
ref class MyClass {
private:
   property ItemType myField;

public:
   property ItemType MyProperty {
      ItemType get() {
         return myField;
      }
      void set(ItemType value) {
         myField = value;
      }
   }
};

int main() {
   MyClass<String^>^ c = gcnew MyClass<String^>();
   MyClass<int>^ c1 = gcnew MyClass<int>();

   c->MyProperty = "John";
   c1->MyProperty = 234;

   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);
}
```

```Output
John, 234
```

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra una clase genérica con un evento.

```cpp
// generics_generic_with_event.cpp
// compile with: /clr
// Declare a generic class with an event and
// invoke events.
using namespace System;

// declare delegates
generic <typename ItemType>
delegate void ClickEventHandler(ItemType);

// generic class that defines events
generic <typename ItemType>
ref class EventSource {
public:
   // declare the event OnClick
   event ClickEventHandler<ItemType>^ OnClick;
   void FireEvents(ItemType item) {
      // raises events
      OnClick(item);
   }
};

// generic class that defines methods that will called when
// event occurs
generic <typename ItemType>
ref class EventReceiver {
public:
   void OnMyClick(ItemType item) {
   Console::WriteLine("OnClick: {0}", item);
   }
};

int main() {
   EventSource<String^>^ MyEventSourceString =
                   gcnew EventSource<String^>();
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();
   EventReceiver<String^>^ MyEventReceiverString =
                   gcnew EventReceiver<String^>();
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();

   // hook handler to event
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);

   // invoke events
   MyEventSourceString->FireEvents("Hello");
   MyEventSourceInt->FireEvents(112);

   // unhook handler to event
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);
}
```

## <a name="generic-structs"></a>Structs genéricos

Las reglas para declarar y usar los structs genéricos son las mismas que las clases genéricas, salvo por las diferencias que anotó en la referencia del lenguaje Visual C++.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara una estructura genérica, `MyGenStruct`, con un campo, `myField`y asigna los valores de tipos diferentes (**int**, **doble**, `String^`) para este campo.

```cpp
// generics_generic_struct1.cpp
// compile with: /clr
using namespace System;

generic <typename ItemType>
ref struct MyGenStruct {
public:
   ItemType myField;

   ItemType AssignValue(ItemType item) {
      myField = item;
      return myField;
   }
};

int main() {
   int myInt = 123;
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();
   myIntObj->AssignValue(myInt);
   Console::WriteLine("The field is assigned the integer value: {0}",
            myIntObj->myField);

   double myDouble = 0.123;
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();
   myDoubleObj->AssignValue(myDouble);
   Console::WriteLine("The field is assigned the double value: {0}",
            myDoubleObj->myField);

   String^ myString = "Hello Generics!";
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();
   myStringObj->AssignValue(myString);
   Console::WriteLine("The field is assigned the string: {0}",
            myStringObj->myField);
}
```

```Output
The field is assigned the integer value: 123
The field is assigned the double value: 0.123
The field is assigned the string: Hello Generics!
```

## <a name="see-also"></a>Vea también

[Genéricos](../windows/generics-cpp-component-extensions.md)