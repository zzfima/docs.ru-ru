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
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792793"
---
# <a name="icordebugnativeframe-interface"></a>Интерфейс ICorDebugNativeFrame

Специализированная реализация ICorDebugFrame, используемая для кадров машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](icordebugnativeframe-cansetip-method.md)|Возвращает значение, указывающее, может ли быть ненадежным устанавливать указатель инструкции на указанное расположение смещения в машинном коде.|  
|[Метод GetIP](icordebugnativeframe-getip-method.md)|Возвращает смещение кадра стека в машинный код.|  
|[Метод GetLocalDoubleRegisterValue](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Возвращает указатель на объект ICorDebugValue, представляющий значение аргумента или локальной переменной, хранящейся в двух регистрах памяти в машинном кадре.|  
|[Метод GetLocalMemoryRegisterValue](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение локальной переменной, для которой младшие биты хранятся в указанном регистре, а старшие биты хранятся по указанному адресу памяти.|  
|[Метод GetLocalMemoryValue](icordebugnativeframe-getlocalmemoryvalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение локальной переменной, хранящейся по указанному адресу памяти.|  
|[Метод GetLocalRegisterMemoryValue](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение локальной переменной, для которой старшие биты хранятся в указанном регистре, а младшие биты хранятся по указанному адресу памяти.|  
|[Метод GetLocalRegisterValue](icordebugnativeframe-getlocalregistervalue-method.md)|Возвращает указатель на `ICorDebugValue`, представляющий значение аргумента или локальную переменную, хранящуюся в указанном собственном регистре.|  
|[Метод GetRegisterSet](icordebugnativeframe-getregisterset-method.md)|Возвращает указатель на объект [ICorDebugRegisterSet](icordebugregisterset-interface.md) , представляющий набор регистров для этого `ICorDebugNativeFrame`.|  
|[Метод SetIP](icordebugnativeframe-setip-method.md)|Задает указатель инструкции в указанном расположении смещения в машинном коде.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
