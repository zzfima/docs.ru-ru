---
title: Интерфейс1 ICorDebugNativeFrame
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c923b54f791cd8ff794538d4687ca0329e62c87e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547031"
---
# <a name="icordebugnativeframe-interface1"></a>Интерфейс1 ICorDebugNativeFrame
Специализированная реализация ICorDebugFrame, используемый для кадров машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод CanSetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Получает значение, указывающее, является ли он безопасным задать указатель инструкций в указанное расположение смещения в машинном коде.|  
|[Метод GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Получает смещение кадра стека в машинный код.|  
|[Метод GetLocalDoubleRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Получает указатель на интерфейс ICorDebugValue, представляющий значение аргумента или локальной переменной, хранящихся в двух регистрах памяти фрейм машинного кода.|  
|[Метод GetLocalMemoryRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Возвращает указатель на `ICorDebugValue` , представляющий значение локальной переменной, которой младшие бита хранятся в указанном регистре, а старшие бита хранятся по адресу указанной области памяти.|  
|[Метод GetLocalMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Возвращает указатель на `ICorDebugValue` , представляющий значение, хранящееся в указанной области памяти адрес локальной переменной.|  
|[Метод GetLocalRegisterMemoryValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Возвращает указатель на `ICorDebugValue` , представляющий значение локальной переменной, которой старшие бита хранятся в указанном регистре, а младшие бита хранятся по указанному адресу памяти|  
|[Метод GetLocalRegisterValue](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Возвращает указатель на `ICorDebugValue` , представляющий значение аргумента или локальной переменной, хранящейся в указанном машинном регистре.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Возвращает указатель на [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , представляющий набор для данного регистров `ICorDebugNativeFrame`.|  
|[Метод SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Задает указатель инструкций в указанное расположение смещения в машинном коде.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
