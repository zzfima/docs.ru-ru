---
title: Интерфейс ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: 8baf3567e4ae188f88ad3a2df157cffab3f597ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125801"
---
# <a name="icordebugchain-interface"></a>Интерфейс ICorDebugChain

Представляет сегмент физического или логического стека вызовов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.|  
|[Метод GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Возвращает активный (то есть самый последний) кадр в цепочке.|  
|[Метод GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Возвращает цепочку, вызванную этой цепочкой.|  
|[Метод GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Возвращает цепочку, вызвавшую эту цепь.|  
|[Метод GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Не реализовано.|  
|[Метод GetNext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Возвращает следующую цепь кадров для потока.|  
|[Метод GetPrevious](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Возвращает предыдущую цепочку кадров для потока.|  
|[Метод GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Возвращает причину женесис данной вызывающей цепочки.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Возвращает набор регистров для активной части этой цепочки.|  
|[Метод GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Возвращает диапазон адресов сегмента стека для этой цепочки.|  
|[Метод GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Возвращает физический поток, частью которого является эта цепочка вызовов.|  
|[Метод IsManaged](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Возвращает значение, указывающее, выполняется ли в этой цепочке управляемый код.|  
  
## <a name="remarks"></a>Заметки  
 Кадры стека в цепочке занимают непрерывное пространство стека и совместно используют один и тот же поток и контекст. Цепочка может представлять как управляемые, так и неуправляемые цепочки кода. Пустой экземпляр `ICorDebugChain` представляет неуправляемую цепочку кода.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
