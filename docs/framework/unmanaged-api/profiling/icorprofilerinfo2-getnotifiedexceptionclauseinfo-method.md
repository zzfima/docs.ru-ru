---
title: Метод ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 52ad124638a1c1ec7d39fa41b9163f3ab50ffe70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433067"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>Метод ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
Получает сведения о машинном адресе и кадре для предложения исключения (`catch`/`finally`/`filter`), которое будет выполняться или только что было запущено.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Параметры  
 `pinfo`  
 заполняет Указатель на структуру [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) , описывающую экземпляр предложения текущего исключения и связанный с ним кадр.  
  
## <a name="remarks"></a>Примечания  
 При получении уведомления об исключении `GetNotifiedExceptionClauseInfo` можно использовать для получения сведений о машинном адресе и кадре для предложения исключения (`catch`/`finally`/`filter`), которое должно быть выполнено (в профилировщике получен обратный вызов[ексцептионкатчерентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md) [или ICorProfilerCallback:](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md): [ексцептионсеарчфилтерентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) ) или только что выполнялось ([ICorProfilerCallback:: ексцептионкатчерлеаве ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), Файловый обратный вызов [ICorProfilerCallback:: Exceptionunwindfinallyleave-](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)или [ICorProfilerCallback:: ексцептионсеарчфилтерлеаве](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) получен профилировщиком).  
  
 Этот вызов можно выполнить в любое время после одного из обратных вызовов при вводе выше, пока не будет получен соответствующий обратный вызов метода Leave или не будет создано вложенное исключение в текущем предложении, в этом случае для этого предложения нет уведомления о выходе. Обратите внимание, что выданное исключение не может покидать предложение `filter` Exception, поэтому в этом случае всегда отображается уведомление о выходе.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
