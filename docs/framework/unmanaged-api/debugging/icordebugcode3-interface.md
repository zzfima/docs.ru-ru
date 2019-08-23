---
title: Интерфейс ICorDebugCode3
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4efcf6d477ab006e179e283ca4ce7b62c27018a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960768"
---
# <a name="icordebugcode3-interface"></a>Интерфейс ICorDebugCode3
Предоставляет метод, который расширяет "ICorDebugCode" и "ICorDebugCode2" для предоставления сведений об управляемом возвращаемом значении.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|Для указанного смещения IL получает машинные смещения, в которых должна быть помещена точка останова, чтобы отладчик мог получить возвращаемое значение из функции.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
