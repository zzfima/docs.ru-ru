---
title: Метод ICorDebugProcess::ModifyLogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 27e13e298c1be61018a92e53a0ee82c786729c7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792588"
---
# <a name="icordebugprocessmodifylogswitch-method"></a>Метод ICorDebugProcess::ModifyLogSwitch
Задает уровень серьезности указанного переключателя журнала.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a>Параметры  
 `pLogSwitchName`  
 окне Указатель на строку, указывающую имя переключателя журнала.  
  
 `lLevel`  
 окне Уровень серьезности, заданный для указанного переключателя журнала.  
  
## <a name="remarks"></a>Заметки  
 Этот метод допустим только после выполнения обратного вызова [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
