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
ms.openlocfilehash: 01c94df1d8e6ddef0110268461a2b28f594201b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue интерфейс1
Представляет значение в отлаживаемом процессе. Значение может быть чтения или записи.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|В настоящее время этот метод не реализован.|  
|[GetAddress-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Возвращает адрес этого `ICorDebugValue` объект, используемый в отлаживаемом процессе.|  
|[GetSize-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Возвращает размер в байтах этого `ICorDebugValue` объекта.|  
|[GetType-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Возвращает тип-примитив `ICorDebugValue` объекта.|  
  
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
