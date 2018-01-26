---
title: "Метод ICorDebugProcess5::EnumerateHeapRegions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeapRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 478a8490e57946a08670d9f86e1f6ebcc67703a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>Метод ICorDebugProcess5::EnumerateHeapRegions
Возвращает перечислитель для диапазона памяти управляемой кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppRegions`  
 [out] Указатель на адрес [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) интерфейс объект, который является перечислителем для диапазонов, в которой находятся объекты в управляемой куче памяти.  
  
## <a name="remarks"></a>Примечания  
 Перед вызовом метода `ICorDebugProcess5::EnumerateHeapRegions` метод, необходимо вызвать [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод и проверьте значение `areGCStructuresValid` поле возвращенного [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Убедитесь, что куче сборщика мусора в ее текущем состоянии перечислимый объект. Кроме того `ICorDebugProcess5::EnumerateHeapRegions` возвращает метод `E_FAIL` при присоединении слишком раннем этапе процесса, прежде чем памяти создаются областей.  
  
 Этот метод гарантируется для перечисления всех областей памяти, которые могут содержать управляемые объекты, но не гарантирует фактически управляемые объекты находятся в этих областях. [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объект коллекции может включать областей памяти пустой или зарезервировано.  
  
 [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объект интерфейса является стандартным перечислителем производными ICorDebugEnum-интерфейс, позволяющий перечислить [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) объектов. Каждый [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) предоставляет сведения о диапазоне памяти конкретного сегмента, а также создания объектов в этом сегменте.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
