---
title: Интерфейс ICorProfilerInfo5
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b249605833e8fbd219495ab92bebc2eff6177eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094259"
---
# <a name="icorprofilerinfo5-interface"></a>Интерфейс ICorProfilerInfo5
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Подкласс [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) , предоставляющий методы для использования профилировщиками кода для взаимодействия с общеязыковой среды выполнения (CLR) для управления отслеживанием событий.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|Получает текущие категории событий, о которых профилировщик хочет принимать уведомления из среды CLR.|  
|[Метод SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|Определяет значение, указывающее типы событий, для которых профилировщик хочет принимать уведомления о событиях от среды CLR.|  
  
## <a name="remarks"></a>Примечания  
 Методы, доступные на этом интерфейсе, предназначены для замены [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) и [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) методы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
