---
title: Las directivas de punto | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2f4b984bcfe1aa89fd8e0229c7381c0d01f8685
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714621"
---
# <a name="dot-directives"></a>Directivas dot

Especificar directivas dot fuera de un bloque de descripción, al principio de una línea. Directivas dot comienzan con un punto (. ) y seguido de dos puntos (:). Se permiten espacios y tabulaciones. Nombres de directiva de punto son distingue mayúsculas de minúsculas y mayúsculas.

|Directiva|Propósito|
|---------------|-------------|
|**. OMITIR:**|Omite los códigos de salida distinto de cero devueltos por comandos, desde el lugar que donde se especifica al final del archivo MAKE. De forma predeterminada, NMAKE se detiene si un comando devuelve un código de salida distinto de cero. Para restaurar la comprobación de errores, use **! CMDSWITCHES**. Para omitir el código de salida para un único comando, use el modificador de guión (-). Para omitir los códigos de salida para un archivo completo, use / me.|
|**. PRECIOSOS:** *destinos*|Conserva *destinos* en disco si se interrumpen los comandos para actualizarlas; no tiene ningún efecto si un comando controla una interrupción eliminando el archivo. Separe los nombres de destino con uno o más espacios o tabulaciones. De forma predeterminada, NMAKE elimina un destino si se interrumpe una compilación mediante CTRL+C o CTRL+INTER. Cada uso de **. PRECIOSAS** se aplica a la totalidad del archivo MAKE; varias especificaciones son acumulativas.|
|**. SILENCIOSA:**|Suprime la presentación de los comandos ejecutados, desde el lugar que donde se especifica al final del archivo MAKE. De forma predeterminada, NMAKE muestra los comandos que invoca. Para restaurar la repetición, use **! CMDSWITCHES**. Para suprimir la repetición de un único comando, use el **@** modificador. Para suprimir la repetición de un archivo completo, utilice/S.|
|**. SUFIJOS:** `list`|Enumera las extensiones para la coincidencia de regla de inferencia; predefinidos para incluir las siguientes extensiones: .exe .obj .asm .c .cpp .cxx BAS Step. para obtener .pas .res .rc .f. f90.|

Para cambiar la **. SUFIJOS** orden de lista o para especificar una lista nueva, borrar la lista y especificar una nueva configuración. Para borrar la lista, no especifique ninguna extensión después de los dos puntos:

```
.SUFFIXES :
```

Para agregar sufijos adicionales al final de la lista, especifique

```
.SUFFIXES : suffixlist
```

donde *suffixlist* es una lista de los sufijos adicionales, separados por uno o más espacios o tabulaciones. Para ver la configuración actual de **. SUFIJOS**, ejecutar NMAKE con/p.

## <a name="see-also"></a>Vea también

[Referencia de NMAKE](../build/nmake-reference.md)