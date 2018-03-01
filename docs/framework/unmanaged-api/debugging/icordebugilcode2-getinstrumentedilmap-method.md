---
title: "Метод ICorDebugILCode2::GetInstrumentedILMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0499813bc2192d419dc21d9dbb84aff17894544f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>Метод ICorDebugILCode2::GetInstrumentedILMap
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 cMap  
 [в] Емкость хранилища массива `map`. Дополнительные сведения см. в разделе "Примечания".  
  
 pcMap  
 [out] Количество значений COR_IL_MAP, записанных в массив сопоставлений.  
  
 map  
 [out] Массив значений COR_IL_MAP, предоставляющие сведения о сопоставлении из Инструментированного профилировщиком промежуточного языка исходного метода.  
  
## <a name="remarks"></a>Примечания  
 Если профилировщик устанавливает сопоставление, вызывая [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) метода, отладчик может вызвать этот метод для извлечения сопоставление и использовать его при вычислении смещений промежуточного языка для стека трассировки и времени существования переменных.  
  
 Если `cMap` равно 0 и `pcMap` не является**null**, `pcMap` равно числу доступных COR_IL_MAP значений. Если значение `cMap` не равно 0, оно обозначает емкость хранилища массива `map`. При возвращении метода `map` содержит более `cMap` элементы, и `pcMap` равно числу значений COR_IL_MAP, фактически записанных `map` массива.  
  
 Если промежуточный язык не инструментирован или профилировщик не предоставил сопоставление, этот метод возвращает значение `S_OK` и присваивает `pcMap` значение 0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [Интерфейс ICorDebugILCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
