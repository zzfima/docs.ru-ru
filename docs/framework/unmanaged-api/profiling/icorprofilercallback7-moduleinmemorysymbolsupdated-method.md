---
title: Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aa690378a32ffee2def672f02dc8b5582647a5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>Метод ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Уведомляет профилировщик при каждом обновлении потока символов, связанного с модулем в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `moduleId`  
 Идентификатор модуля в памяти, обновление которого поток символов.  
  
## <a name="remarks"></a>Примечания  
 Этот обратный вызов можно изменять, задавая [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) флага маски события при вызове [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.  
  
> [!NOTE]
>  Это событие не происходит в данный момент для символов, неявно созданного или измененного через <xref:System.Reflection.Emit> API-интерфейсы.  
  
 Даже если символы предоставляются заранее при обращении к одной из перегрузок управляемых <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> методов, включая `rawSymbolStore` аргумент, чтобы указать символы для сборки, среда выполнения может не связать фактически символьных данных в модуле пока после [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) произошла обратного вызова. Это событие предоставляет более поздней версии возможность сбора символы для таких модулей.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [Метод SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [Интерфейс ICorProfilerCallback7](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
