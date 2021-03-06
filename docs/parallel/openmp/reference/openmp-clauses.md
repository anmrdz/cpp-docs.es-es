---
title: Cláusulas de OpenMP | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- if
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
dev_langs:
- C++
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea394ca09a086229a8718f4e7e1bfa55115652bc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056228"
---
# <a name="openmp-clauses"></a>Cláusulas de OpenMP

Proporciona vínculos a las cláusulas que se utilizan en la API de OpenMP.

Visual C++ admite las cláusulas de OpenMP siguientes:

|Cláusula|Descripción|
|------|-----------|
|[copyin](#copyin)|Permite que los subprocesos tener acceso a valor del subproceso principal, para un [threadprivate](openmp-directives.md#threadprivate) variable.|
|[copyprivate](#copyprivate)|Especifica que una o más variables deben compartirse entre todos los subprocesos.|
|[default](#default-openmp)|Especifica el comportamiento de las variables sin ámbito de una región paralela.|
|[firstprivate](#firstprivate)|Especifica que cada subproceso debe tener su propia instancia de una variable, y que la variable debe inicializarse con el valor de la variable, porque existe antes de la construcción paralela.|
|[if](#if-openmp)|Especifica si se debe ejecutar un bucle en paralelo o en serie.|
|[lastprivate](#lastprivate)|Especifica que versión envolvente del contexto de la variable se establece igual que la versión privada de cualquier subproceso que ejecuta la última iteración (construcción de bucle for) o la última sección (#pragma secciones).|
|[nowait](#nowait)|Invalida la barrera implícita en una directiva.|
|[num_threads](#num-threads)|Establece el número de subprocesos en un equipo de subproceso.|
|[Ordenada](#ordered-openmp-clauses)|Necesario en un paralelo [para](openmp-directives.md#for-openmp) instrucción si un [ordenados](openmp-directives.md#ordered-openmp-directives) directiva es que se usará en el bucle.|
|[private](#private-openmp)|Especifica que cada subproceso debe tener su propia instancia de una variable.|
|[reduction](#reduction)|Especifica que una o más variables que son privadas para cada subproceso se el sujeto de una operación de reducción al final de la región paralela.|
|[schedule](#schedule)|Se aplica a la [para](openmp-directives.md#for-openmp) directiva.|
|[Compartido](#shared-openmp)|Especifica que una o más variables deben compartirse entre todos los subprocesos.|

## <a name="copyin"></a>copyin

Permite que los subprocesos tener acceso a valor del subproceso principal, para un [threadprivate](openmp-directives.md#threadprivate) variable.

```
copyin(var)
```

### <a name="parameters"></a>Parámetros

*var*<br/>
El `threadprivate` variable que se inicializará con el valor de la variable en el subproceso principal, tal como existe antes de la construcción paralela.

### <a name="remarks"></a>Comentarios

`copyin` se aplica a las siguientes directivas:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).

### <a name="example"></a>Ejemplo

Consulte [threadprivate](openmp-directives.md#threadprivate) para obtener un ejemplo del uso de `copyin`.

## <a name="copyprivate"></a>copyprivate

Especifica que una o más variables deben compartirse entre todos los subprocesos.

```
copyprivate(var)
```

### <a name="parameters"></a>Parámetros

*var*<br/>
Una o más variables para compartir. Si se especifica más de una variable, separe los nombres de variable con una coma.

### <a name="remarks"></a>Comentarios

`copyprivate` se aplica a la [único](openmp-directives.md#single) directiva.

Para obtener más información, consulte [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md).

### <a name="example"></a>Ejemplo

```
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default-openmp"></a>predeterminado (OpenMP)

Especifica el comportamiento de las variables sin ámbito de una región paralela.

```
default(shared | none)
```

### <a name="remarks"></a>Comentarios

`shared`, que está en vigor si el `default` cláusula no se especifica, significa que cualquier variable en una región paralela se tratará como si se especificó con el [compartido](#shared-openmp) cláusula. `none` significa que las variables utilizadas en una región paralela que no están en el ámbito con la [privada](#private-openmp), [compartido](#shared-openmp), [reducción](#reduction), [firstprivate](#firstprivate), o [lastprivate](#lastprivate) cláusula provocará un error del compilador.

`default` se aplica a las siguientes directivas:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.7.2.5 predeterminada](../../../parallel/openmp/2-7-2-5-default.md).

### <a name="example"></a>Ejemplo

Consulte [privada](#private-openmp) para obtener un ejemplo del uso de `default`.

## <a name="firstprivate"></a>firstprivate

Especifica que cada subproceso debe tener su propia instancia de una variable, y que la variable debe inicializarse con el valor de la variable, porque existe antes de la construcción paralela.

```
firstprivate(var)
```

### <a name="parameters"></a>Parámetros

*var*<br/>
La variable a tener instancias en cada subproceso y se inicializará con el valor de la variable, porque existe antes de la construcción paralela. Si se especifica más de una variable, separe los nombres de variable con una coma.

### <a name="remarks"></a>Comentarios

`firstprivate` se aplica a las siguientes directivas:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [Secciones](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Para obtener más información, consulte [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).

### <a name="example"></a>Ejemplo

Para obtener un ejemplo del uso de `firstprivate`, vea el ejemplo de [privada](#private-openmp).

## <a name="if-openmp"></a>Si (OpenMP)

Especifica si se debe ejecutar un bucle en paralelo o en serie.

```
if(expression)
```

### <a name="parameters"></a>Parámetros

*Expresión*<br/>
Una expresión entera que, si se evalúa como True (distinto de cero,) hace que el código en la región paralela para ejecutar en paralelo. Si la expresión se evalúa como false (cero), la región paralela se ejecuta en serie (mediante un único subproceso).

### <a name="remarks"></a>Comentarios

`if` se aplica a las siguientes directivas:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.3 parallel (construcción)](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Ejemplo

```
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a>lastprivate

Especifica que versión envolvente del contexto de la variable se establece igual que la versión privada de cualquier subproceso que ejecuta la última iteración (construcción de bucle for) o la última sección (#pragma secciones).

```
lastprivate(var)
```

### <a name="parameters"></a>Parámetros

*var*<br/>
La variable que se establece igual que la versión privada de cualquier subproceso que ejecuta la última iteración (construcción de bucle for) o la última sección (#pragma secciones).

### <a name="remarks"></a>Comentarios

`lastprivate` se aplica a las siguientes directivas:

- [for](openmp-directives.md#for-openmp)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).

### <a name="example"></a>Ejemplo

Consulte [programación](#schedule) para obtener un ejemplo del uso de `lastprivate` cláusula.

## <a name="nowait"></a>NOWAIT

Invalida la barrera implícita en una directiva.

```
nowait
```

### <a name="remarks"></a>Comentarios

`nowait` se aplica a las siguientes directivas:

- [for](openmp-directives.md#for-openmp)
- [Secciones](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Para obtener más información, consulte [2.4.1 for (construcción)](../../../parallel/openmp/2-4-1-for-construct.md), [2.4.2 sections (construcción)](../../../parallel/openmp/2-4-2-sections-construct.md), y [2.4.3 single construir](../../../parallel/openmp/2-4-3-single-construct.md).

### <a name="example"></a>Ejemplo

```
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num-threads"></a>num_threads

Establece el número de subprocesos en un equipo de subproceso.

```
num_threads(num)
```

### <a name="parameters"></a>Parámetros

*num*<br/>
El número de subprocesos

### <a name="remarks"></a>Comentarios

El `num_threads` cláusula tiene la misma funcionalidad que el [omp_set_num_threads ()](openmp-functions.md#omp-set-num-threads) función.

`num_threads` se aplica a las siguientes directivas:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.3 parallel (construcción)](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Ejemplo

Consulte [paralelo](openmp-directives.md#parallel) para obtener un ejemplo del uso de `num_threads` cláusula.

## <a name="ordered-openmp-clauses"></a>ordered (cláusulas de OpenMP)

Necesario en un paralelo [para](openmp-directives.md#for-openmp) instrucción si un [ordenados](openmp-directives.md#ordered-openmp-directives) directiva es que se usará en el bucle.

```
ordered
```

### <a name="remarks"></a>Comentarios

`ordered` se aplica a la [para](openmp-directives.md#for-openmp) directiva.

Para obtener más información, consulte [2.4.1 for (construcción)](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Ejemplo

Consulte [ordenados](openmp-directives.md#ordered-openmp-directives) para obtener un ejemplo del uso de `ordered` cláusula.

## <a name="private-openmp"></a>Private (OpenMP)

Especifica que cada subproceso debe tener su propia instancia de una variable.

```
private(var)
```

### <a name="parameters"></a>Parámetros

*var*<br/>
La variable para tener instancias en cada subproceso.

### <a name="remarks"></a>Comentarios

`private` se aplica a las siguientes directivas:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [Secciones](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Para obtener más información, consulte [2.7.2.1 privada](../../../parallel/openmp/2-7-2-1-private.md).

### <a name="example"></a>Ejemplo

```C
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a>reducción

Especifica que una o más variables que son privadas para cada subproceso se el sujeto de una operación de reducción al final de la región paralela.

```
reduction(operation:var)
```

### <a name="parameters"></a>Parámetros

*Operación*<br/>
El operador para la operación de hacer en las variables (`var`) al final de la región paralela.

*var*<br/>
Una o más variables en el que se va a realizar la reducción escalar. Si se especifica más de una variable, separe los nombres de variable con una coma.

### <a name="remarks"></a>Comentarios

`reduction` se aplica a las siguientes directivas:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.7.2.6 reducción](../../../parallel/openmp/2-7-2-6-reduction.md).

### <a name="example"></a>Ejemplo

```
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a>Programación

Se aplica a la [para](openmp-directives.md#for-openmp) directiva.

```
schedule(type[,size])
```

### <a name="parameters"></a>Parámetros

*type*<br/>
El tipo de programación:

- `dynamic`
- `guided`
- `runtime`
- `static`

*size*<br/>
(Opcional) Especifica el tamaño de las iteraciones. `size` debe ser un entero. No es válido cuando `type` es `runtime`.

### <a name="remarks"></a>Comentarios

Para obtener más información, consulte [2.4.1 for (construcción)](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Ejemplo

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------

```

## <a name="shared-openmp"></a>compartido (OpenMP)

Especifica que una o más variables deben compartirse entre todos los subprocesos.

```
shared(var)
```

### <a name="parameters"></a>Parámetros

*var*<br/>
Una o más variables para compartir. Si se especifica más de una variable, separe los nombres de variable con una coma.

### <a name="remarks"></a>Comentarios

Otra manera de compartir variables entre subprocesos es con el [copyprivate](#copyprivate) cláusula.

`shared` se aplica a las siguientes directivas:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [Secciones](openmp-directives.md#sections-openmp)

Para obtener más información, consulte [2.7.2.4 compartido](../../../parallel/openmp/2-7-2-4-shared.md).

### <a name="example"></a>Ejemplo

Consulte [privada](#private-openmp) para obtener un ejemplo del uso de `shared`.
