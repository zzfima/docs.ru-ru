---
title: Метод ICorDebugILCode2::GetInstrumentedILMap
ms.date: 03/30/2017
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
ms.openlocfilehash: 7dede4e5af702f1b86b430450db4a669c326c062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131063"
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
  
## <a name="parameters"></a>Параметры  
 cMap  
 [в] Емкость хранилища массива `map`. Дополнительные сведения см. в разделе "Примечания".  
  
 pcMap  
 заполняет Число значений COR_IL_MAP, записанных в массив сопоставлений.  
  
 map  
 заполняет Массив значений COR_IL_MAP, которые предоставляют сведения о сопоставлениях из инструментированного профилировщика IL с IL исходного метода.  
  
## <a name="remarks"></a>Заметки  
 Если профилировщик задает сопоставление путем вызова метода [ICorProfilerInfo:: сетилинструментедкодемап](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , отладчик может вызвать этот метод, чтобы получить сопоставление и использовать внутреннее сопоставление при вычислении смещений Il для трассировок стека и переменной. время существования.  
  
 Если `cMap` имеет значение 0, а `pcMap` не равно**null**, для `pcMap` задается количество доступных значений COR_IL_MAP. Если значение `cMap` не равно 0, оно обозначает емкость хранилища массива `map`. Когда метод возвращает значение, `map` содержит максимум `cMap` элементов, а `pcMap` задает количество значений COR_IL_MAP, фактически записанных в массив `map`.  
  
 Если промежуточный язык не инструментирован или профилировщик не предоставил сопоставление, этот метод возвращает значение `S_OK` и присваивает `pcMap` значение 0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [ICorProfilerInfo:: Сетилинструментедкодемап](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [Интерфейс ICorDebugILCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
