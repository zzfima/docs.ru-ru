---
title: Интерфейс ICorDebugRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6419a525a8a542295751defb97e67a83220730b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965070"
---
# <a name="icordebugregisterset-interface"></a>Интерфейс ICorDebugRegisterSet
Представляет набор регистров, доступных на компьютере, который выполняет код в данный момент.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|Возвращает значение каждого регистра (на компьютере, выполняющем в данный момент код), который задается битовой маской.|  
|[Метод GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|Возвращает битовую маску, указывающую, какие `ICorDebugRegisterSet` регистры в данный момент доступны.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|Возвращает контекст текущего потока.|  
|[Метод SetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|Не реализовано для .NET Framework версии 2,0.|  
|[Метод SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|Не реализовано для .NET Framework 2,0.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugRegisterSet` Интерфейс поддерживает только 32-разрядные регистры. Используйте интерфейс [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) на платформах, таких как IA-64, требующих дополнительных регистров.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
