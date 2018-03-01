---
title: "ICorDebugFrame интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: caa3ef9cd52cc872d4ebc96376c104a7b90fb4f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframe-interface1"></a>ICorDebugFrame интерфейс1
Представляет кадр текущего стека.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Возвращает ICorDebugStepper осуществлять пошаговое выполнение операций относительно это `ICorDebugFrame`.|  
|[Метод GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепи, вызванной этим кадром, или возвращает значение null, если это самый внутренний кадр в цепочке.|  
|[Метод GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепи, вызванной этим кадром, или возвращает значение null, если это самый внешний кадр в цепочке.|  
|[Метод GetChain](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Получает указатель на ICorDebugChain это `ICorDebugFrame` является частью.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Возвращает указатель на интерфейс ICorDebugCode, связанный с данным кадром стека.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Возвращает указатель на ICorDebugFunction, который содержит код, связанный с данным кадром стека.|  
|[Метод GetFunctionToken](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Получает маркер метаданных для функции, которая содержит код, связанный с данным кадром стека.|  
|[Метод GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Возвращает диапазон абсолютных адресов кадра стека, представленный этим `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
