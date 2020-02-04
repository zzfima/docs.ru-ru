---
title: Структура COR_PRF_EX_CLAUSE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: fb6d2e5fc21047fea0928137f983c553f9bb2bbd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867286"
---
# <a name="cor_prf_ex_clause_info-structure"></a>Структура COR_PRF_EX_CLAUSE_INFO
Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`clauseType`|Значение перечисления [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) , указывающее тип предложения исключения, введенного или левого кода.|  
|`programCounter`|Собственная точка входа обработчика предложения, например, содержимое регистра x86 EIP.|  
|`framePointer`|Указатель на логический кадр для обработчика предложения, например содержимое регистра x86 EBP.|  
|`shadowStackPointer`|Указатель на теневой стек. Это значение является содержимым регистра BSP и применяется только к версии IA64.|  
  
## <a name="remarks"></a>Заметки  
 При получении уведомления об исключении можно использовать [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) для получения сведений о собственном адресе и кадре для предложения исключения (`catch`/`finally`/Filter), которое будет выполняться или только что было запущено.  
  
 Выполнение предложения исключения включает следующие обратные вызовы из среды CLR:  
  
- [ICorProfilerCallback:: Ексцептионкатчерентер](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионунвиндфиналлентер](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионсеарчфилтерентер](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионкатчерлеаве](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [ICorProfilerCallback:: Exceptionunwindfinallyleave-](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [ICorProfilerCallback:: Ексцептионсеарчфилтерлеаве](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структуры профилирования](profiling-structures.md)
