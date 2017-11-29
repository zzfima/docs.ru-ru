---
title: "Структура CorDebugBlockingObject"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingObject Structure
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingObject
helpviewer_keywords: CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c47735565c960c2600f7274d0d59d5a6ec6c178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingobject-structure"></a>Структура CorDebugBlockingObject
Определяет объект, блокирующий поток и конкретную причину блокировки потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`pBlockingObject`|Объект, на котором блокирован поток. Этот объект действителен только в течение текущего синхронизированного состояния. Если два потока блокируются на одном объекте в одном синхронизированном состоянии, можно ожидать [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) метод, чтобы возвращать то же значение. Однако интерфейсы могут находиться не эквивалентность указателей.|  
|`dwTimeout`|Количество миллисекунд до операции блокирования будет время ожидания, или значение INFINITE, означающее, что он имеет неограниченное время ожидания. Значение времени ожидания указывает общую длину время операции блокировки, а не осталось времени.|  
|`blockingReason`|Причина, что поток заблокирован для этого объекта.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
