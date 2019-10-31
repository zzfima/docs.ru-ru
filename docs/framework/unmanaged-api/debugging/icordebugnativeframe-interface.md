---
title: Интерфейс ICorDebugNativeFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 04bdbc49217236bc6c05a718cb4d42067cafd8bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096672"
---
# <a name="icordebugnativeframe-interface"></a>Интерфейс ICorDebugNativeFrame

Специализированная реализация ICorDebugFrame, используемая для кадров машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Возвращает значение, указывающее, может ли быть ненадежным устанавливать указатель инструкции на указанное расположение смещения в машинном коде.|  
|[Метод GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Возвращает смещение кадра стека в машинный код.|  
|[Метод GetLocalDoubleRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Возвращает указатель на объект ICorDebugValue, представляющий значение аргумента или локальной переменной, хранящейся в двух регистрах памяти в машинном кадре.|  
|[Метод GetLocalMemoryRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение локальной переменной, для которой младшие биты хранятся в указанном регистре, а старшие биты хранятся по указанному адресу памяти.|  
|[Метод GetLocalMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение локальной переменной, хранящейся по указанному адресу памяти.|  
|[Метод GetLocalRegisterMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение локальной переменной, для которой старшие биты хранятся в указанном регистре, а младшие биты хранятся по указанному адресу памяти.|  
|[Метод GetLocalRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение аргумента или локальную переменную, хранящуюся в указанном собственном регистре.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Возвращает указатель на объект [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , представляющий набор регистров для этого `ICorDebugNativeFrame`.|  
|[Метод SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Задает указатель инструкции в указанном расположении смещения в машинном коде.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
