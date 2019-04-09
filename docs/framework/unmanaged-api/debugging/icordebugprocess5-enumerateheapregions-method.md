---
title: Метод ICorDebugProcess5::EnumerateHeapRegions
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61e30cf4ffe45578f7ad37de8295d227dbf313c9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103965"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>Метод ICorDebugProcess5::EnumerateHeapRegions
Возвращает перечислитель для диапазона памяти управляемой кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppRegions`  
 [out] Указатель на адрес [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объект интерфейса, который является перечислителем для диапазонов адресов памяти, в котором находятся объекты в управляемой куче.  
  
## <a name="remarks"></a>Примечания  
 Перед вызовом `ICorDebugProcess5::EnumerateHeapRegions` метод следует вызывать [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод и проверьте значение `areGCStructuresValid` поле возвращенного [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Объект, чтобы убедиться, что в ее текущем состоянии куче сбора мусора является перечислимым. Кроме того `ICorDebugProcess5::EnumerateHeapRegions` возвращает метод `E_FAIL` при присоединении слишком раннем этапе жизни процесса, прежде чем памяти регионах создаются.  
  
 Этот метод гарантированно перечисления всех областей памяти, которые могут содержать управляемые объекты, но это не гарантирует, что управляемые объекты располагаются в этих регионах. [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объект коллекции могут быть пустой или зарезервированный памяти регионы.  
  
 [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объект интерфейс является производным от ICorDebugEnum интерфейс, который позволяет перечислять стандартный перечислитель [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) объектов. Каждый [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) объект предоставляет сведения о диапазоне памяти конкретного сегмента, а также поколение объектов, в этом сегменте.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
