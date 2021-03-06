---
title: C4800 de advertencias del compilador a través de C5999 | Microsoft Docs
ms.date: 10/24/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
- C4807
- C4808
- C4809
- C4810
- C4811
- C4812
- C4813
- C4816
- C4817
- C4822
- C4825
- C4827
- C4837
- C4841
- C4842
- C4843
- C4844
- C4872
- C4880
- C4881
- C4882
- C4900
- C4910
- C4912
- C4913
- C4916
- C4918
- C4920
- C4921
- C4925
- C4926
- C4932
- C4934
- C4935
- C4936
- C4937
- C4938
- C4939
- C4944
- C4947
- C4950
- C4951
- C4952
- C4953
- C4954
- C4955
- C4956
- C4957
- C4958
- C4959
- C4960
- C4961
- C4962
- C4963
- C4966
- C4970
- C4971
- C4972
- C4973
- C4974
- C4981
- C4985
- C4987
- C4988
- C4989
- C4990
- C4991
- C4992
- C4997
- C4998
- C4999
- C5022
- C5023
- C5024
- C5025
- C5026
- C5027
- C5028
- C5029
- C5030
- C5031
- C5032
- C5033
- C5034
- C5035
- C5036
- C5037
- C5039
- C5040
- C5041
- C5042
- C5043
- C5044
- C5045
- C5046
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27f212865965883732e8bd956cafecf50e0a8de3
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990352"
---
# <a name="compiler-warnings-c4800-through-c5999"></a>C4800 de advertencias del compilador a través de C5999

Los artículos de esta sección de la documentación explican un subconjunto de los mensajes de advertencia generados por el compilador.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Mensajes de advertencia

|Advertencia|Mensaje|
|-------------|-------------|
|[Advertencia del compilador (nivel 3) C4800](compiler-warning-level-3-c4800.md)|'*tipo*': forzar que el valor booleano 'true' o 'false' (advertencia de rendimiento)|
|[Advertencia del compilador (nivel 1) C4803](compiler-warning-level-1-c4803.md)|'*método*': el método raise tiene una clase de almacenamiento distinta de la del evento, '*eventos*'|
|[Advertencia del compilador (nivel 1) C4804](compiler-warning-level-1-c4804.md)|'*operación*': uso no seguro del tipo 'bool' en la operación|
|[Advertencia del compilador (nivel 1) C4805](compiler-warning-level-1-c4805.md)|'*operación*': combinación no segura del tipo '*type1*'y tipo'*type2*' en la operación|
|Advertencia del compilador (nivel 1) C4806|'*operación*': operación no segura: ningún valor de tipo '*type1*'promovido al tipo'*type2*' puede igualar la constante proporcionada|
|Advertencia del compilador (nivel 1) C4807|'*operación*': combinación no segura del tipo '*type1*'y firmado el campo de bits de tipo'*type2*'|
|Advertencia del compilador (nivel 1) C4808|caso '*valor*' es el valor no válido para la condición switch de tipo 'bool'|
|Advertencia del compilador (nivel 1) C4809|instrucción switch tiene una etiqueta 'default' redundante; se proporcionan todas las etiquetas 'case' posibles|
|Advertencia del compilador (nivel 1) C4810|valor de pragma pack(show) == n|
|Advertencia del compilador (nivel 1) C4811|valor de pragma conform(forScope, show) == %s|
|Advertencia del compilador (nivel 1) C4812|estilo de declaración obsoleto: utilice '*new_syntax*' en su lugar|
|Advertencia del compilador (nivel 1) C4813|'*función*': debe haber declarado anteriormente una función friend de una clase local|
|Advertencia del compilador (nivel 4) C4816|'*param*': el parámetro tiene una matriz de tamaño cero que se truncará (a menos que el objeto se pasa por referencia)|
|Advertencia del compilador (nivel 1) C4817|'*miembro*': uso no válido de '.' para obtener acceso a este miembro; el compilador lo reemplazó por '->'|
|[Advertencia del compilador (nivel 1) C4819](compiler-warning-level-1-c4819.md)|El archivo contiene un carácter que no se puede representar en la página de códigos actual (número). Guarde el archivo en formato Unicode para evitar la pérdida de datos|
|[Advertencia del compilador (nivel 4) C4820](compiler-warning-level-4-c4820.md)|'*bytes*'bytes de relleno agregados después de la construcción'*member_name*'|
|[Advertencia del compilador (nivel 1) C4821](compiler-warning-level-1-c4821.md)|No se puede determinar el tipo de codificación Unicode guarde el archivo con signatura (BOM)|
|Advertencia del compilador (nivel 1) C4822|'member function': función miembro de clase local no tiene un cuerpo|
|[Advertencia del compilador (nivel 3) C4823](compiler-warning-level-3-c4823.md)|'*función*': utiliza punteros anclados pero desenredo semántica no está habilitada. Considere el uso de /EHa|
|Advertencia del compilador (nivel 2) C4826|Conversión de '*type1*'para'*type2*' extensión de signo. Esto puede provocar un comportamiento inesperado en tiempo de ejecución.|
|Advertencia del compilador (nivel 3) C4827|Un método 'ToString' público con 0 parámetros debe marcarse como virtual y reemplazar|
|[Advertencia del compilador (nivel 1) C4829](compiler-warning-level-1-c4829.md)|Parámetros posiblemente incorrectos para la función main. Considere ' int main (Platform:: Array\<Platform:: String ^ > ^ argv)'|
|[Advertencia del compilador (nivel 1) C4835](compiler-warning-level-1-c4835.md)|'*variable*': el inicializador para los datos exportados no se ejecutará hasta que el código administrado se ejecuta en primer lugar en el ensamblado de host|
|Advertencia del compilador (nivel 4) C4837|se detectó un trígrafo: '?? *carácter*'reemplazado por'*carácter*'|
|[Advertencia del compilador (nivel 1) C4838](compiler-warning-level-1-c4838.md)|conversión de '*type_1*'para'*type_2*' requiere una conversión de restricción|
|[Advertencia del compilador (nivel 3) C4839](compiler-warning-level-3-c4839.md)|uso no estándar de la clase*tipo*' como argumento a una función variádica|
|[Advertencia del compilador (nivel 4) C4840](compiler-warning-level-4-c4840.md)|uso no portable de la clase*tipo*' como argumento a una función variádica|
|Advertencia del compilador (nivel 4) C4841|extensión no estándar utilizada: designador de miembro compuesto utilizado en offsetof|
|Advertencia del compilador (nivel 4) C4842|no se garantiza el resultado de "offsetof" aplicada a un tipo mediante herencia múltiple sea consistente con las versiones del compilador|
|Advertencia C4843 del compilador|'*type1*': un controlador de excepciones de referencia al tipo de matriz o función no es accesible, use '*type2*' en su lugar|
|Advertencia C4844 del compilador|"Exportar módulo *module_name*;' es ahora la sintaxis recomendada para declarar una interfaz de módulo|
|[Advertencia del compilador (nivel 4) C4866](c4866.md)| compilador no puede aplicar el orden de evaluación de izquierda a derecha de la llamada a *nombre_operador*|
|[Advertencia (Error) del compilador C4867](compiler-warning-c4867.md)|'*función*': falta la lista de argumentos de llamada de función; utilice '*llamar*' para crear un puntero a miembro|
|[Advertencia (nivel 4) del compilador C4868](compiler-warning-c4868.md)|'_archivo_(*line_number*)' compilador no puede aplicar el orden de evaluación de izquierda a derecha en la lista de inicialización entre llaves|
|Advertencia del compilador (nivel 2) C4872|división de punto flotante por cero detectado al compilar el gráfico de llamadas para Concurrency:: parallel_for_each en: '*ubicación*'|
|Advertencia del compilador (nivel 1) C4880|realiza la conversión de ' const *type_1*'para'*type_2*': desechar la declaración de un puntero o referencia puede provocar un comportamiento indefinido en una función de la restricción de amp|
|Advertencia del compilador (nivel 4) C4881|el constructor o destructor no se invocará para la variable tile_static '*variable*'|
|Advertencia del compilador (nivel 1) C4882|pasar objetos functor con operadores de llamada no constantes a Concurrency:: parallel_for_each está en desuso|
|Advertencia C4900 del compilador|Error de coincidencia de IL entre '*tool1*'version'*version1*'y'*tool2*'version'*version2*'|
|[Advertencia del compilador (nivel 1) C4905](compiler-warning-level-1-c4905.md)|conversión de literal de cadena de tipo ancho a 'LPSTR'|
|[Advertencia del compilador (nivel 1) C4906](compiler-warning-level-1-c4906.md)|conversión de literal de cadena a 'LPWSTR'|
|Advertencia del compilador (nivel 1) C4910|'\<identificador >: '__declspec (dllexport)' y 'extern' son incompatibles en una instancia explícita|
|Advertencia del compilador (nivel 1) C4912|'*atributo*': atributo de comportamiento no definido en un UDT anidado|
|Advertencia del compilador (nivel 4) C4913|el operador binario ',' definido por el usuario existe pero ninguna sobrecarga puede convertir todos los operandos; en su lugar, se utilizará el operador binario ',' incorporado|
|Advertencia del compilador (nivel 1) C4916|para tener un dispid, '*descripción*': debe ser producido por una interfaz|
|[Advertencia del compilador (nivel 1) C4917](compiler-warning-level-1-c4917.md)|'*declarador*': un GUID solo puede asociarse con una clase, interfaz o espacio de nombres|
|Advertencia del compilador (nivel 4) C4918|'*carácter*': carácter no válido en la lista de optimizaciones de pragma|
|Advertencia del compilador (nivel 1) C4920|enum enum miembro member_1 = value_1 ya se ha visto en enum enum como member_2 = value_2|
|Advertencia del compilador (nivel 3) C4921|'*descripción*': valor del atributo '*atributo*' no se debe especificar varias veces|
|Advertencia del compilador (nivel 1) C4925|'*método*': no se puede llamar al método dispinterface desde el script|
|Advertencia del compilador (nivel 1) C4926|'*identificador*': ya se ha definido el símbolo: omitido los atributos|
|[Advertencia del compilador (nivel 1) C4927](compiler-warning-level-1-c4927.md)|conversión no válida; se aplicó implícitamente más de una conversión definida por el usuario|
|[Advertencia del compilador (nivel 1) C4928](compiler-warning-level-1-c4928.md)|inicialización de copia no válida; se aplicó implícitamente más de una conversión definida por el usuario|
|[Advertencia del compilador (nivel 1) C4929](compiler-warning-level-1-c4929.md)|'*archivo*': biblioteca de tipos contiene una unión; se omitirá el calificador 'embedded_idl'|
|[Advertencia del compilador (nivel 1) C4930](compiler-warning-level-1-c4930.md)|'*prototipo*': no se llama a la función prototipo (era pensada una definición de variable?)|
|[Advertencia del compilador (nivel 4) C4931](compiler-warning-level-4-c4931.md)|se supone que la biblioteca de tipos se compiló para punteros de (número) bits|
|Advertencia del compilador (nivel 4) C4932|__identifier (*identificador*) y \__identificador (*identificador*) son indistinguibles|
|Advertencia del compilador (nivel 1) C4934|'__delegate (Multicast)' está en desuso, utilice '\__delegate' en su lugar|
|Advertencia del compilador (nivel 1) C4935|especificador de acceso de ensamblado modificado de '*acceso*'|
|Advertencia del compilador (nivel 1, Error) C4936|__declspec se admite solamente cuando se compila con /clr o /clr:pure|
|Advertencia del compilador (nivel 4) C4937|'*text1*'y'*text2*'son pueden distinguir como argumentos a'*directiva*'|
|Advertencia del compilador (nivel 4) C4938|'*var*': variable de reducción de punto flotante puede causar resultados incoherentes bajo/fp: strict o #pragma fenv_access|
|Advertencia C4939 del compilador|#pragma vtordisp está en desuso y se quitará en una próxima versión de Visual C++|
|Advertencia del compilador (nivel 1) C4944|'*símbolo*': no se puede importar un símbolo desde '*assembly1*': como*símbolo*' ya existe en el ámbito actual|
|[Advertencia del compilador (nivel 1) C4945](compiler-warning-level-1-c4945.md)|'*símbolo*': no se puede importar un símbolo desde '*assembly1*': como*símbolo*'ya se importó desde otro ensamblado'*assembly2* '|
|[Advertencia del compilador (nivel 1) C4946](compiler-warning-level-1-c4946.md)|se utilizó reinterpret_cast entre clases relacionadas: '*class1*'y'*class2*'|
|Advertencia del compilador (nivel 1) C4947|'*type_or_member*': marcado como obsoleto|
|[Advertencia del compilador (nivel 2) C4948](compiler-warning-level-2-c4948.md)|tipo de valor devuelto '*descriptor de acceso*' no coincide con el tipo último parámetro de un establecedor correspondiente|
|[Advertencia del compilador (niveles 1 y 4) C4949](compiler-warning-level-1-and-level-4-c4949.md)|pragmas 'managed' y 'unmanaged' solamente son significativas cuando se compilan con ' / clr [: opción]'|
|Advertencia del compilador (nivel 1, Error) C4950|'*type_or_member*': marcado como obsoleto|
|Advertencia del compilador (nivel 1) C4951|'*función*' se ha editado desde que se recopilaron los datos, los datos de perfil de función no usa de perfil|
|Advertencia del compilador (nivel 1) C4952|'*función*': se encontró ningún perfil de datos en la base de datos de programa '*archivo_pgd*'|
|Advertencia del compilador (nivel 1) C4953|Inlinee '*función*' se ha editado desde que se recopilaron los datos, datos de perfil no utilizados de perfil|
|Advertencia C4954 del compilador|'*función*': no perfilado (contiene la expresión switch __int64)|
|Advertencia C4955 del compilador|'*import2*': importación omitida; ya se importó desde '*import1*'|
|Advertencia del compilador (nivel 1, Error) C4956|'*tipo*': este tipo no es comprobable|
|Advertencia del compilador (nivel 1, Error) C4957|'*cast*': conversión explícita de '*cast_from*'para'*cast_to*' no es comprobable|
|Advertencia del compilador (nivel 1, Error) C4958|'*operación*': la aritmética con punteros no es comprobable|
|Advertencia del compilador (nivel 1, Error) C4959|no se puede definir el tipo no administrado '*tipo*' en/CLR: safe porque el acceso a sus miembros proporciona código no comprobable|
|Advertencia del compilador (nivel 4) C4960|'*función*' es demasiado grande para generar un perfil|
|Advertencia del compilador (nivel 1) C4961|No se combinó ningún dato de perfil en 'archivo .pgd'; se han deshabilitado las optimizaciones guiadas por perfil.|
|Advertencia del compilador (nivel 4) C4962|'*función*': las optimizaciones guiadas por perfil deshabilitadas porque generaban datos de perfil incoherentes|
|Advertencia del compilador (nivel 1) C4963|'*descripción*': se encontró ningún perfil de datos; se utilizaron opciones de compilador diferentes en la compilación instrumentada|
|[Advertencia del compilador (nivel 1) C4964](compiler-warning-level-1-c4964.md)|Se especificó ninguna opción de optimización; no se recopilará la información de perfil|
|[Advertencia del compilador (nivel 1) C4965](compiler-warning-level-1-c4965.md)|conversión boxing implícita de entero 0; Utilice nullptr o conversión explícita|
|Advertencia del compilador (nivel 1) C4966|'*función*' tiene una anotación __code_seg con nombre de segmento no admitido; anotación omitida|
|Advertencia C4970 del compilador|constructor delegado: objeto de destino se omite desde '*tipo*' es estático|
|Advertencia del compilador (nivel 1) C4971|Orden de argumentos: \<objeto de destino >, \<función de destino > para el constructor delegado está en desuso, utilice \<función de destino >, \<objeto de destino = "" >|
|Advertencia del compilador (nivel 1, Error) C4972|No se puede comprobar la modificación o el tratamiento directo del resultado de una operación de conversión unbox como valor L|
|Advertencia del compilador (nivel 1) C4973|'*símbolo*': marcado como en desuso|
|Advertencia del compilador (nivel 1) C4974|'*símbolo*': marcado como en desuso|
|Advertencia del compilador (nivel 3) C4981|Warbird: función '*función*' marcada como __forceinline no está entre líneas porque contiene semántica de excepción|
|Advertencia del compilador (nivel 3) C4985|nombre del símbolo ': atributos no presentes en la declaración anterior.|
|[Advertencia del compilador C4986](compiler-warning-c4986.md)|'*declaración*': especificación de excepción no coincide con la declaración anterior|
|Advertencia del compilador (nivel 4) C4987|se usó una extensión no estándar: 'throw (...)'|
|Advertencia del compilador (nivel 4) C4988|'*variable*': variable declarada fuera del ámbito de clase o función|
|Advertencia del compilador (nivel 4) C4989|'*tipo*': tipo tiene definiciones en conflicto.|
|Advertencia del compilador (nivel 3) C4990|Warbird: *mensaje*|
|Advertencia del compilador (nivel 3) C4991|Warbird: función '*función*' marcada como __forceinline no entre líneas porque el nivel de protección de inlinee es mayor que el elemento primario|
|Advertencia del compilador (nivel 3) C4992|Warbird: función '*función*' marcada como __forceinline no entre líneas porque contiene un ensamblado alineado que no se puede proteger|
|[Advertencia del compilador (nivel 3) C4995](compiler-warning-level-3-c4995.md)|'*función*': se marcó el nombre como #pragma deprecated|
|[Advertencia del compilador (nivel 3) C4996](compiler-warning-level-3-c4996.md)|'*descripción*': *mensaje*|
|Advertencia del compilador (nivel 1) C4997|'*clase*': coclase no implementa una pseudointerfaz o interfaz COM|
|Advertencia del compilador (nivel 1) C4998|Error de EXPECTATIVA: *expectativa*(*valor*)|
|Advertencia C4999 del compilador|Advertencia desconocida elija el comando soporte técnico en el menú Ayuda de Visual C++, o abra el archivo de Ayuda de soporte técnico para obtener más información|
|Advertencia C5022 del compilador|'*tipo*': han especificado varios constructores de movimiento|
|Advertencia C5023 del compilador|'*tipo*': varios operadores de asignación especificados|
|Advertencia del compilador (nivel 4) C5024|'*tipo*': mueva el constructor se definió implícitamente como eliminado|
|Advertencia del compilador (nivel 4) C5025|'*tipo*': mover operador de asignación se definió implícitamente como eliminado|
|Advertencia del compilador (niveles 1 y 4) C5026|'*tipo*': mueva el constructor se definió implícitamente como eliminado|
|Advertencia del compilador (niveles 1 y 4) C5027|'*tipo*': mover operador de asignación se definió implícitamente como eliminado|
|Advertencia del compilador (nivel 1) C5028|'*nombre*': especifica la alineación en una declaración anterior (*número*) no se especifica en la definición|
|Advertencia del compilador (nivel 4) C5029|extensión no estándar utilizada: los atributos de alineación en C++ se aplican a variables, los miembros de datos y solo los tipos de etiquetas|
|Advertencia del compilador (nivel 3) C5030|atributo '*atributo*' no se reconoce|
|Advertencia del compilador (nivel 4) C5031|#pragma warning (POP): probable desajuste, extraer el estado de advertencia insertado en otro archivo|
|Advertencia del compilador (nivel 4) C5032|detectado #pragma warning (Push) con ningún Warning (POP) #pragma correspondiente|
|Advertencia del compilador (nivel 1) C5033|'*clase de almacenamiento*' ya no es una clase de almacenamiento compatibles|
|Advertencia C5034 del compilador|el uso de la función intrínseca '*intrínseco*' hace que la función *función* se compile como código invitado|
|Advertencia C5035 del compilador|el uso de la característica '*característica*' hace que la función *función* se compile como código invitado|
|Advertencia del compilador (nivel 1) C5036|conversión de puntero a la función de varargs al compilar con/Hybrid: x86arm64 '*type1*'para'*type2*'|
|Advertencia del compilador C5037 (error)|'*función miembro*': una definición fuera de línea de un miembro de una plantilla de clase no puede tener argumentos predeterminados|
|[Advertencia del compilador (nivel 4) C5038](c5038.md)|miembro de datos '*member1*'se inicializará después del miembro de datos'*member2*'|
|Advertencia del compilador (nivel 4) C5039|'*función*': puntero o referencia a una función de inicio potencialmente pasa a la función de C externa en EHc-. Si esta función produce una excepción, puede producirse un comportamiento indefinido.|
|Advertencia del compilador (nivel 3) C5040|especificaciones de excepción dinámicas son válidas únicamente en C ++ 14 y versiones anteriores; tratar como noexcept (false)|
|Advertencia del compilador (nivel 1) C5041|'*definición*': definición fuera de línea para un miembro de datos estático constexpr no es necesaria y está en desuso en C ++ 17|
|Advertencia del compilador (nivel 3) C5042|'*declaración*': las declaraciones de función en el ámbito de bloque no pueden ser 'inline' especificado en el estándar de C++; quite el especificador "inline"|
|Advertencia del compilador (nivel 2) los errores C5043|'*especificación*': especificación de excepción no coincide con la declaración anterior|
|Advertencia del compilador (nivel 4) C5044|Un argumento de opción de línea de comandos *opción* apunta a una ruta de acceso '*ruta*' que no existe|
|[C5045 de advertencia del compilador](c5045.md)|Compilador insertará la mitigación de Spectre para la carga de memoria si el modificador/qspectre especificado.|
|[Advertencia del compilador (nivel 2) C5046](c5046.md)|'*función*': símbolo de que impliquen tipo con vinculación interna no definido|
