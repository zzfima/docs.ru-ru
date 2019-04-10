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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01dded47fca26df11781153eb45693057a25ad01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220712"
---
# <a name="icordebugchain-interface"></a>Интерфейс ICorDebugChain

Представляет сегмент физического или логического стека вызовов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего.|  
|[Метод GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Получает активный (то есть самой последней) кадра в цепочке.|  
|[Метод GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Получает цепочку, вызванная этой цепочки.|  
|[Метод GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Получает цепочку, вызвавшей эту цепочку.|  
|[Метод GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Не реализовано.|  
|[Метод GetNext](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Получает следующую цепь кадров для потока.|  
|[Метод GetPrevious](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Получает предыдущий цепочки кадров для потока.|  
|[Метод GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Получает причину происхождения этой цепочки вызовов.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Получает набор регистров для активной части этой цепочки.|  
|[Метод GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Получает диапазон адресов сегмента стека для этой цепочки.|  
|[Метод GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Получает часть физических обсуждение, на которое эта цепочка вызовов.|  
|[Метод IsManaged](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Получает значение, указывающее, выполняется ли эта цепочка управляемого кода.|  
  
## <a name="remarks"></a>Примечания  
 Кадры стека в цепочке занимают непрерывное пространство стека и используют один поток и контекст. Цепь может представлять любой цепочки управляемого или неуправляемого кода. Пустой `ICorDebugChain` экземпляр представляет созданию цепочки неуправляемого кода.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
