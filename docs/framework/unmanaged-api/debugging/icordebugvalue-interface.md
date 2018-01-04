---
title: "ICorDebugValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue
helpviewer_keywords: ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3464b4ad963b2fe764cefc5868440b7748f8c4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue интерфейс1
Представляет значение в отлаживаемом процессе. Значение может быть чтения или записи.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|В настоящее время этот метод не реализован.|  
|[Метод GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Возвращает адрес этого `ICorDebugValue` объект, используемый в отлаживаемом процессе.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Возвращает размер в байтах этого `ICorDebugValue` объекта.|  
|[Метод GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Возвращает тип-примитив `ICorDebugValue` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Как правило владение объектом значение передается при возврате. Получатель отвечает за удаление ссылки из объекта при его завершении с объектом.  
  
 В зависимости от того, где значение было получено путем значение может оказаться недействительным после возобновления процесса. Таким образом, как правило, значения не должны храниться во время вызова из [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
    
    
    
    
 [Интерфейс ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
