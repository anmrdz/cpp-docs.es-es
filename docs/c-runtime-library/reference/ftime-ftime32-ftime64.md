---
title: _ftime, _ftime32, _ftime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ftime64
- _ftime
- _ftime32
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
dev_langs:
- C++
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8942dbaddcc1f4ab1ec5d571d08d95d8669d302d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107060"
---
# <a name="ftime-ftime32-ftime64"></a>_ftime, _ftime32, _ftime64

Obtenga la hora actual. Hay disponibles versiones más seguras de estas funciones; consulte [_ftime_s, _ftime32_s, _ftime64_s](ftime-s-ftime32-s-ftime64-s.md).

## <a name="syntax"></a>Sintaxis

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parámetros

*timeptr*<br/>
Puntero a un **_timeb**, **__timeb32**, o **__timeb64** estructura.

## <a name="remarks"></a>Comentarios

El **_ftime** función obtiene la hora local actual y lo almacena en la estructura que señala *timeptr*. El **_timeb**, **__timeb32**, y **__timeb64** estructuras se definen en \<sys\\timeb.h >. Contienen cuatro campos, que se enumeran en la tabla siguiente.

|Campo|Descripción|
|-|-|
|**dstflag**|Distinto de cero si el horario de verano está en vigor para la zona horaria local. (Consulte [_tzset](tzset.md) para obtener una explicación de cómo se determina el horario de verano).|
|**millitm**|Fracción de segundo en milisegundos.|
|**time**|La hora en segundos desde la medianoche (00:00:00) del 1 de enero de 1970, hora universal coordinada (UTC).|
|**Zona horaria**|Diferencia en minutos, que se desplaza hacia el oeste, entre la hora UTC y la hora local. El valor de **timezone** se establece el valor de la variable global **_timezone** (consulte **_tzset**).|

El **_ftime64** función, que usa el **__timeb64** estructura, permite la creación del archivo fechas expresarse a través de 23:59:59, 31 de diciembre de 3000, UTC; mientras que **_ftime32**solo representa fechas hasta las 23:59:59 del 18 de enero de 2038, UTC. La medianoche del 1 de enero de 1970 es el límite inferior del intervalo de fechas para todas estas funciones.

El **_ftime** es equivalente a la función **_ftime64**, y **_timeb** contiene una hora de 64 bits, a menos que **_USE_32BIT_TIME_T** se define, en cuyo caso el comportamiento anterior está en vigor; **_ftime** usa un tiempo de 32 bits y **_timeb** contiene un tiempo de 32 bits.

**_ftime** valida sus parámetros. Si pasa un puntero nulo como *timeptr*, la función invoca al controlador de parámetros no válidos, tal y como se describe en [validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, la función establece **errno** a **EINVAL**.

## <a name="requirements"></a>Requisitos

|Función|Encabezado necesario|
|--------------|---------------------|
|**_ftime**|\<sys/types.h> y \<sys/timeb.h>|
|**_ftime32**|\<sys/types.h> y \<sys/timeb.h>|
|**_ftime64**|\<sys/types.h> y \<sys/timeb.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Ejemplo

```C
// crt_ftime.c
// compile with: /W3
// This program uses _ftime to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime( &timebuffer ); // C4996
   // Note: _ftime is deprecated; consider using _ftime_s instead

   time1 = timebuffer.time;
   millitm1 = timebuffer.millitm;
   timezone1 = timebuffer.timezone;
   dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>Vea también

[Administración del tiempo](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
