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
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="b64f1-102">Структура COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="b64f1-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="b64f1-103">Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="b64f1-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b64f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b64f1-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b64f1-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b64f1-105">Members</span></span>  
  
|<span data-ttu-id="b64f1-106">Член</span><span class="sxs-lookup"><span data-stu-id="b64f1-106">Member</span></span>|<span data-ttu-id="b64f1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b64f1-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="b64f1-108">Значение перечисления [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) , указывающее тип предложения исключения, введенного или левого кода.</span><span class="sxs-lookup"><span data-stu-id="b64f1-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="b64f1-109">Собственная точка входа обработчика предложения, например, содержимое регистра x86 EIP.</span><span class="sxs-lookup"><span data-stu-id="b64f1-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="b64f1-110">Указатель на логический кадр для обработчика предложения, например содержимое регистра x86 EBP.</span><span class="sxs-lookup"><span data-stu-id="b64f1-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="b64f1-111">Указатель на теневой стек.</span><span class="sxs-lookup"><span data-stu-id="b64f1-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="b64f1-112">Это значение является содержимым регистра BSP и применяется только к версии IA64.</span><span class="sxs-lookup"><span data-stu-id="b64f1-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b64f1-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b64f1-113">Remarks</span></span>  
 <span data-ttu-id="b64f1-114">При получении уведомления об исключении можно использовать [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) для получения сведений о собственном адресе и кадре для предложения исключения (`catch`/`finally`/Filter), которое будет выполняться или только что было запущено.</span><span class="sxs-lookup"><span data-stu-id="b64f1-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="b64f1-115">Выполнение предложения исключения включает следующие обратные вызовы из среды CLR:</span><span class="sxs-lookup"><span data-stu-id="b64f1-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="b64f1-116">ICorProfilerCallback:: Ексцептионкатчерентер</span><span class="sxs-lookup"><span data-stu-id="b64f1-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="b64f1-117">ICorProfilerCallback:: Ексцептионунвиндфиналлентер</span><span class="sxs-lookup"><span data-stu-id="b64f1-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="b64f1-118">ICorProfilerCallback:: Ексцептионсеарчфилтерентер</span><span class="sxs-lookup"><span data-stu-id="b64f1-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="b64f1-119">ICorProfilerCallback:: Ексцептионкатчерлеаве</span><span class="sxs-lookup"><span data-stu-id="b64f1-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="b64f1-120">ICorProfilerCallback:: Exceptionunwindfinallyleave-</span><span class="sxs-lookup"><span data-stu-id="b64f1-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="b64f1-121">ICorProfilerCallback:: Ексцептионсеарчфилтерлеаве</span><span class="sxs-lookup"><span data-stu-id="b64f1-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="b64f1-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b64f1-122">Requirements</span></span>  
 <span data-ttu-id="b64f1-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b64f1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b64f1-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="b64f1-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b64f1-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b64f1-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b64f1-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b64f1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64f1-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b64f1-127">See also</span></span>

- [<span data-ttu-id="b64f1-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="b64f1-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
