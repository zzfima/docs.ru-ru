---
title: Перечисление CorDebugThreadState
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2296f6e386f35aed91a8aea4392a9cd00ec27ccb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724370"
---
# <a name="cordebugthreadstate-enumeration"></a>Перечисление CorDebugThreadState
Указывает состояние потока для отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`THREAD_RUN`|Поток выполняется свободно, пока не произойдет событие отладки.|  
|`THREAD_SUSPEND`|Не удается запустить поток.|  
  
## <a name="remarks"></a>Примечания  
 Отладчик использует `CorDebugThreadState` перечисления для контроля потока выполнения. Состояние потока, можно задать с помощью [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) или [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) метод.  
  
 Обратный вызов, предоставленный [интерфейс API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md) позволяет выдачи сообщений, поэтому состояния прерванного не требуется.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDegug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
