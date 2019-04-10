---
title: Интерфейс ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227825"
---
# <a name="icordebugvalue-interface"></a>Интерфейс ICorDebugValue
Представляет значение в отлаживаемом процессе. Значение может быть чтения или записи.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|В настоящее время этот метод не реализован.|  
|[Метод GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Возвращает адрес это `ICorDebugValue` объект, который находится в отлаживаемом процессе.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Получает размер в байтах, это `ICorDebugValue` объекта.|  
|[Метод GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Получает тип-примитив это `ICorDebugValue` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Как правило владение объектом значение передается при возврате. Получатель отвечает за удаление ссылки из объекта при его завершении с объектом.  
  
 В зависимости от того, где значение было получено путем значение может не остаются действительными после возобновления процесса. Таким образом, как правило, значение не должно храниться во время вызова из [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
