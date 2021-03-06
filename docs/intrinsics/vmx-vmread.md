---
title: __vmx_vmread | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9483dafd763112f31f5299a5e0e7e54c224459
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821028"
---
# <a name="vmxvmread"></a>__vmx_vmread

**Específicos de Microsoft**

Lee un campo especificado de la estructura de control de máquina virtual (VMCS) actual y lo coloca en la ubicación especificada.

## <a name="syntax"></a>Sintaxis

```
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

#### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*Campo*|[in] El campo VMCS a leer.|
|*FieldValue*|[in] Lee un puntero a la ubicación para almacenar el valor del campo VMCS especificado por el `Field` parámetro.|

## <a name="return-value"></a>Valor devuelto

|Valor|Significado|
|-----------|-------------|
|0|La operación se realizó correctamente.|
|1|Error en la operación con el estado extendido disponible en el `VM-instruction error field` de la VMCS actual.|
|2|Error en la operación sin estado disponible.|

## <a name="remarks"></a>Comentarios

El `__vmx_vmread` función es equivalente a la `VMREAD` instrucción máquina. El valor de la `Field` parámetro es un índice de campo codificado que se describe en la documentación de Intel. Para obtener más información, busque el documento, "Intel Virtualization Technical especificación para la arquitectura IA-32 Intel," documento C97063-002, número en el [Intel Corporation](https://software.intel.com/articles/intel-sdm) de sitio, a continuación, consulte el apéndice C de ese documento .

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__vmx_vmread`|x64|

**Archivo de encabezado** \<intrin.h >

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)