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
ms.openlocfilehash: df4bfe69b22439073342693a03376a0b506f9c70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428371"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`clauseType`|Значение перечисления [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) , указывающее тип предложения исключения, введенного или левого кода.|  
|`programCounter`|Собственная точка входа обработчика предложения, например, содержимое регистра x86 EIP.|  
|`framePointer`|Указатель на логический кадр для обработчика предложения, например содержимое регистра x86 EBP.|  
|`shadowStackPointer`|Указатель на теневой стек. Это значение является содержимым регистра BSP и применяется только к версии IA64.|  
  
## <a name="remarks"></a>Примечания  
 При получении уведомления об исключении можно использовать [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) для получения сведений о собственном адресе и кадре для предложения исключения (`catch`/`finally`/Filter), которое будет выполняться или только что было запущено.  
  
 Выполнение предложения исключения включает следующие обратные вызовы из среды CLR:  
  
- [ICorProfilerCallback:: Ексцептионкатчерентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионунвиндфиналлентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионсеарчфилтерентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback:: Ексцептионкатчерлеаве](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [ICorProfilerCallback:: Exceptionunwindfinallyleave-](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [ICorProfilerCallback:: Ексцептионсеарчфилтерлеаве](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
