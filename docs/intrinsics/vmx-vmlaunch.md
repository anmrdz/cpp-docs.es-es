---
title: __vmx_vmlaunch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmlaunch
dev_langs:
- C++
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9519250684ea4f354c2ccfbca5be64076d6376d6
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820586"
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch

**Específicos de Microsoft**

Coloca la aplicación que realiza la llamada en estado de operación que no es de raíz VMX (máquina virtual escriba) mediante el uso de la estructura de control de máquina virtual (VMCS) actual.

## <a name="syntax"></a>Sintaxis

```
unsigned char __vmx_vmlaunch(
   void);
```

## <a name="return-value"></a>Valor devuelto

|Valor|Significado|
|-----------|-------------|
|0|La operación se realizó correctamente.|
|1|Error en la operación con el estado extendido disponible en el `VM-instruction error field` de la VMCS actual.|
|2|Error en la operación sin estado disponible.|

## <a name="remarks"></a>Comentarios

Una aplicación puede realizar una operación de entrada en máquina virtual mediante el uso del [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) o [__vmx_vmresume](../intrinsics/vmx-vmresume.md) función. El [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) función puede utilizarse solo con una VMCS cuyo estado de inicio es `Clear`y el [__vmx_vmresume](../intrinsics/vmx-vmresume.md) función puede utilizarse solo con una VMCS cuyo estado de inicio es `Launched`. Por lo tanto, use el [__vmx_vmclear](../intrinsics/vmx-vmclear.md) función para establecer el estado de inicio de una VMCS en `Clear`y, a continuación, utilice el [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) función para la primera operación escriba a la máquina virtual y el [__vmx_vmresume](../intrinsics/vmx-vmresume.md) función para operaciones posteriores.

El `__vmx_vmlaunch` función es equivalente a la `VMLAUNCH` instrucción máquina. Esta función admite la interacción del monitor de máquina virtual de un host con un sistema operativo invitado y sus aplicaciones. Para obtener más información, busque el documento, "Intel Virtualization Technical especificación para la arquitectura IA-32 Intel," documento C97063-002, número en el [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitio.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__vmx_vmlaunch`|x64|

**Archivo de encabezado** \<intrin.h >

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)<br/>
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)