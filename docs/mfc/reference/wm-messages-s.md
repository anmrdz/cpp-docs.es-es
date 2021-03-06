---
title: 'Mensajes WM_: S | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_SIZE [MFC]
- ON_WM_SETFOCUS [MFC]
- ON_WM_SIZING [MFC]
- ON_WM_SYSCHAR [MFC]
- ON_WM_SETTINGCHANGE [MFC]
- ON_WM_SYSDEADCHAR [MFC]
- ON_WM_SHOWWINDOW [MFC]
- ON_WM_STYLECHANGING [MFC]
- ON_WM_SYSCOMMAND [MFC]
- ON_WM_STYLECHANGED [MFC]
- ON_WM_SPOOLERSTATUS [MFC]
- ON_WM_SYSCOLORCHANGE [MFC]
- ON_WM_SETCURSOR [MFC]
- ON_WM_SIZECLIPBOARD [MFC]
- ON_WM_SYSKEYUP [MFC]
- ON_WM_SYSKEYDOWN [MFC]
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e554fb119d8476761f612bb021d6ca17d1baeb1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410226"
---
# <a name="wm-messages-s"></a>WM_ Messages: S

Las entradas de asignación siguientes corresponden a los prototipos de función.

|Entrada de asignación|Prototipo de función|
|---------------|------------------------|
|(DE ON_WM_SETCURSOR)|afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, UINT, UINT);|
|(DE ON_WM_SETFOCUS)|void afx_msg [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|
|(DE ON_WM_SETTINGCHANGE)|void afx_msg [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)(UINT uFlags, LPCTSTR lpszSection);|
|(DE ON_WM_SHOWWINDOW)|void afx_msg [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(BOOL, UINT);|
|(DE ON_WM_SIZE)|void afx_msg [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT, int, int);|
|(DE ON_WM_SIZECLIPBOARD)|void afx_msg [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, identificador);|
|(DE ON_WM_SIZING)|void afx_msg [OnDestroy](../../mfc/reference/cwnd-class.md#onsizing)(UINT, LPRECT);|
|(DE ON_WM_SPOOLERSTATUS)|void afx_msg [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)(UINT, UINT);|
|(DE ON_WM_STYLECHANGED)|void afx_msg [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(int, LPSTYLESTRUCT);|
|(DE ON_WM_STYLECHANGING)|void afx_msg [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)(int, LPSTYLESTRUCT);|
|(DE ON_WM_SYSCHAR)|void afx_msg [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)(UINT, UINT, UINT);|
|(DE ON_WM_SYSCOLORCHANGE)|void afx_msg [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|
|(DE ON_WM_SYSCOMMAND)|void afx_msg [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, LONG);|
|(DE ON_WM_SYSDEADCHAR)|void afx_msg [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)(UINT, UINT, UINT);|
|(DE ON_WM_SYSKEYDOWN)|void afx_msg [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)(UINT, UINT, UINT);|
|(DE ON_WM_SYSKEYUP)|void afx_msg [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)(UINT, UINT, UINT);|

## <a name="see-also"></a>Vea también

[Mapas de mensajes](../../mfc/reference/message-maps-mfc.md)<br/>
[Controladores de mensajes WM_](../../mfc/reference/handlers-for-wm-messages.md)

