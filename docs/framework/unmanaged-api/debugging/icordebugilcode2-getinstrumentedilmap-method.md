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
ms.openlocfilehash: 728a6c83dc321fa28dc4ff84c4e874d886524b36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788562"
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
 [в] Емкость хранилища массива `map`. Дополнительные сведения см. в разделе «Примечания».  
  
 pcMap  
 [из] Количество значений COR_IL_MAP, записанных в массив сопоставлений.  
  
 map  
 [из] Массив значений COR_IL_MAP, предоставляющий информацию о сопоставлениях промежуточного языка, инструментированного профилировщиком, и промежуточного языка исходного метода.  
  
## <a name="remarks"></a>Заметки  
 Если профилировщик задает сопоставление путем вызова метода [ICorProfilerInfo:: сетилинструментедкодемап](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , отладчик может вызвать этот метод, чтобы получить сопоставление и использовать внутреннее сопоставление при вычислении смещений Il для трассировок стека и времени существования переменных.  
  
 Если `cMap` имеет значение 0, а `pcMap` не равно**null**, для `pcMap` задается количество доступных COR_IL_MAP значений. Если значение `cMap` не равно 0, оно обозначает емкость хранилища массива `map`. Когда метод возвращает значение, `map` содержит максимум `cMap` элементов, а `pcMap` задает количество COR_IL_MAP значений, фактически записанных в массив `map`.  
  
 Если промежуточный язык не инструментирован или профилировщик не предоставил сопоставление, этот метод возвращает значение `S_OK` и присваивает `pcMap` значение 0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [ICorProfilerInfo:: Сетилинструментедкодемап](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
