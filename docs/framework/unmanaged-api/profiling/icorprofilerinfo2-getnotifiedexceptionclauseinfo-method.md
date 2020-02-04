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
ms.openlocfilehash: a430631948230d16e5d04c869625b4c670faaf02
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868646"
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
 заполняет Указатель на структуру [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) , описывающую экземпляр предложения текущего исключения и связанный с ним кадр.  
  
## <a name="remarks"></a>Заметки  
 При получении уведомления об исключении `GetNotifiedExceptionClauseInfo` можно использовать для получения сведений о машинном адресе и кадре для предложения исключения (`catch`/`finally`/`filter`), которое должно быть выполнено (в профилировщике получен обратный вызов[ексцептионкатчерентер](icorprofilercallback-exceptioncatcherenter-method.md) [или ICorProfilerCallback:](icorprofilercallback-exceptionunwindfinallyenter-method.md): [ексцептионсеарчфилтерентер](icorprofilercallback-exceptionsearchfilterenter-method.md) ) или только что выполнялось ([ICorProfilerCallback:: ексцептионкатчерлеаве ](icorprofilercallback-exceptioncatcherleave-method.md), Файловый обратный вызов [ICorProfilerCallback:: Exceptionunwindfinallyleave-](icorprofilercallback-exceptionunwindfinallyleave-method.md)или [ICorProfilerCallback:: ексцептионсеарчфилтерлеаве](icorprofilercallback-exceptionsearchfilterleave-method.md) получен профилировщиком).  
  
 Этот вызов можно выполнить в любое время после одного из обратных вызовов при вводе выше, пока не будет получен соответствующий обратный вызов метода Leave или не будет создано вложенное исключение в текущем предложении, в этом случае для этого предложения нет уведомления о выходе. Обратите внимание, что выданное исключение не может покидать предложение `filter` Exception, поэтому в этом случае всегда отображается уведомление о выходе.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
