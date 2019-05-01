---
title: Метод ICorProfilerInfo5::SetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266219894ffefa0d4066c6ca68c7cadf6265e098
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000484"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a>Метод ICorProfilerInfo5::SetEventMask2
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Определяет значение, указывающее типы событий, для которых профилировщик хочет получать уведомления о событиях от среды CLR. Он предоставляет больше возможностей, чем [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwEventsLow`  
 [в] 4-байтовое значение, определяющее категории событий. Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.  
  
 `dwEventsHigh`  
 [в] 4-байтовое значение, определяющее категории событий.  Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) перечисления.  
  
## <a name="remarks"></a>Примечания  
 Метод `SetEventMask2` используется для установки обратных вызовов, на которые подписывается профилировщик. Как правило, вызывается [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) метод, чтобы определить, какие биты установлены, выполнять логическое или для его `pdwEventsLow` и `pdwEventsHigh` значения и новых битов, вы хотите, а затем вызовите `SetEventMask2` метод.  
  
 Этот метод является рекомендуемой альтернативой для [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [Метод GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
