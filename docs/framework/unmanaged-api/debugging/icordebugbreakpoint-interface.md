---
title: "ICorDebugBreakpoint интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b78b61b99fb8f236e787f3acbf993d0a1c57e797
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpoint-interface1"></a>ICorDebugBreakpoint интерфейс1
Представляет точку останова в функции или контрольную точку значение.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Activate-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Задает активное состояние `ICorDebugBreakpoint`.|  
|[IsActive-метод](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Возвращает значение, указывающее, является ли это `ICorDebugBreakpoint` активен.|  
  
## <a name="remarks"></a>Примечания  
 Точки останова напрямую не поддерживают условные выражения. При необходимости такие функциональные возможности, отладчик должен реализовать его на основе `ICorDebugBreakpoint`.  
  
 Icordebugfunctionbreakpoint-интерфейс расширяет `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
