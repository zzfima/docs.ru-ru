---
title: Метод ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: 1190f83e2671216cf1627eeb710ba576e4b2ec93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125360"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>Метод ICorDebugController::SetAllThreadsDebugState
Задает состояние отладки всех управляемых потоков в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `state`  
 окне Значение перечисления "Кордебугсреадстате", указывающее состояние потока для отладки.  
  
 `pExceptThisThread`  
 окне Указатель на объект "ICorDebugThread", представляющий поток, исключаемый из параметра состояния отладки. Если это значение равно null, ни один поток не исключен.  
  
## <a name="remarks"></a>Заметки  
 Метод `SetAllThreadsDebugState` может повлиять на потоки, которые не видны через [метод енумератесреадс](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), поэтому потоки, которые были приостановлены с помощью метода `SetAllThreadsDebugState`, необходимо возобновить с помощью метода `SetAllThreadsDebugState`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
