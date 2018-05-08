---
title: Метод ICorProfilerInfo5::GetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8973e100694be0f50b575d978f3327b8b3a1d334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>Метод ICorProfilerInfo5::GetEventMask2
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.  Он предоставляет функциональные возможности, не предоставляемые [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pdwEventsLow`  
 [из] Указатель на 4-байтовое значение, определяющее категории событий. Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.  
  
 `pdwEventsHigh`  
 [из] Указатель на 4-байтовое значение, определяющее категории событий.  Каждый бит управляет отдельной возможностью, поведением или типом события. Биты описаны в [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) перечисления.  
  
## <a name="remarks"></a>Примечания  
 Метод `GetEventMask2` используется для определения обратных вызовов, на которые подписался профилировщик. Обычно для выполнения логического OR `pdwEventsLow` и `pdwEventsHigh` значения и новых битов, нужно установить, а затем вызвать [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод.  
  
 Этот метод — это рекомендуемая альтернатива для [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [Метод SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
