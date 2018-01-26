---
title: "Структура COR_SEGMENT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9414aa1c36ba059d9ee1101f6183dc8a669f9e6f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corsegment-structure"></a>Структура COR_SEGMENT
Содержит сведения об области памяти в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`start`|Начальный адрес области памяти.|  
|`end`|Конечный адрес области памяти.|  
|`gen`|Объект [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) член перечисления, указывающее, создание области памяти.|  
|`heap`|Номер кучи, в которой находится в области памяти. Дополнительные сведения см. в разделе "Примечания".|  
  
## <a name="remarks"></a>Примечания  
 `COR_SEGMENTS` Структура представляет области памяти в управляемой куче.  `COR_SEGMENTS`объекты являются элементами [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объекта коллекции, который заполняется путем вызова[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) метод.  
  
 `heap` Поле является число процессоров, соответствующее кучи формируется отчет. Для сборщиков мусора рабочей станции его значение всегда равно нулю, так как рабочие станции имеют только один кучи сборщика мусора. Для сборщиков мусора сервера его значение соответствует кучи, подключенный к процессору. Обратите внимание, что может больше или меньше мусора кучи чем фактическое процессоров из-за особенностей реализации сборщика мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
