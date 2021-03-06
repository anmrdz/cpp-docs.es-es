---
title: double_2 (clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp_short_vectors/Concurrency::graphics::double_2::set_x
- amp_short_vectors/Concurrency::graphics::double_2::operator+=
- amp_short_vectors/Concurrency::graphics::double_2::operator=
- amp_short_vectors/Concurrency::graphics::double_2::operator/=
- amp_short_vectors/Concurrency::graphics::double_2::operator*=
- amp_short_vectors/Concurrency::graphics::double_2::yx
- amp_short_vectors/Concurrency::graphics::double_2::y
- amp_short_vectors/Concurrency::graphics::double_2::xy
- amp_short_vectors/Concurrency::graphics::double_2::set_xy
- amp_short_vectors/Concurrency::graphics::double_2::get_yx
- amp_short_vectors/Concurrency::graphics::double_2::set_yx
- amp_short_vectors/Concurrency::graphics::double_2::get_xy
- amp_short_vectors/Concurrency::graphics::double_2::operator++
- amp_short_vectors/Concurrency::graphics::double_2::get_x
- amp_short_vectors/Concurrency::graphics::double_2::operator-=
- amp_short_vectors/Concurrency::graphics::double_2::rg
- amp_short_vectors/Concurrency::graphics::double_2::gr
- amp_short_vectors/Concurrency::graphics::double_2::get_y
- amp_short_vectors/Concurrency::graphics::double_2::x
- amp_short_vectors/Concurrency::graphics::double_2::r
- amp_short_vectors/Concurrency::graphics::double_2::operator--
- amp_short_vectors/Concurrency::graphics::double_2
- amp_short_vectors/Concurrency::graphics::double_2::operator-
- amp_short_vectors/Concurrency::graphics::double_2::g
- amp_short_vectors/Concurrency::graphics::double_2::set_y
dev_langs:
- C++
ms.assetid: c19c2d21-3cbf-4ce5-b460-3b8253688f82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2091c6d76cfd139d9e842c26bfbffb3e556b050
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411175"
---
# <a name="double2-class"></a>double_2 (Clase)

Representa un vector corto de 2 dobles.

## <a name="syntax"></a>Sintaxis

```
class double_2;
```

## <a name="members"></a>Miembros

### <a name="public-typedefs"></a>Definiciones de tipos públicas

|Name|Descripción|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[Constructor double_2](#ctor)|Sobrecargado. El constructor predeterminado, inicializa todos los elementos con 0.|

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|double_2:: get_X||
|double_2::get_xy||
|double_2:: get_Y||
|double_2::get_yx||
|double_2:: ref_g||
|double_2::ref_r||
|double_2:: ref_x||
|double_2:: ref_y||
|double_2::set_x||
|double_2::set_xy||
|double_2:: set_y||
|double_2::set_yx||

### <a name="public-operators"></a>Operadores públicos

|Name|Descripción|
|----------|-----------------|
|double_2::operator-||
|double_2::operator--||
|double_2::operator*=||
|operador double_2:: / =||
|operador double_2:: ++||
|double_2::operator+=||
|double_2::operator=||
|double_2::operator-=||

### <a name="public-constants"></a>Constantes públicas

|nombre|Descripción|
|----------|-----------------|
|double_2::size (Constante)||

### <a name="public-data-members"></a>Miembros de datos públicos

|Name|Descripción|
|----------|-----------------|
|double_2:: g||
|double_2:: GR||
|double_2:: r||
|double_2:: RG||
|double_2:: x||
|double_2:: XY||
|double_2:: y||
|double_2:: YX||

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`double_2`

## <a name="requirements"></a>Requisitos

**Encabezado:** amp_short_vectors.h

**Namespace:** Concurrency:: Graphics

##  <a name="ctor"></a> double_2

El constructor predeterminado, inicializa todos los elementos con 0.

```
double_2() restrict(amp,
    cpu);

double_2(
    double _V0,
    double _V1) restrict(amp,
    cpu);

double_2(
    double _V) restrict(amp,
    cpu);

double_2(
    const double_2& _Other) restrict(amp,
    cpu);

explicit inline double_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline double_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline double_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline double_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline double_2(
    const norm_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parámetros

*_V0*<br/>
El valor para inicializar el elemento 0.

*_V1*<br/>
El valor para inicializar el elemento 1.

*_V*<br/>
El valor de inicialización.

*_Otro*<br/>
El objeto usado para inicializar.

##  <a name="double_2__size"></a> Tamaño

```
static const int size = 2;
```

## <a name="see-also"></a>Vea también

[Concurrency::graphics (espacio de nombres)](concurrency-graphics-namespace.md)
