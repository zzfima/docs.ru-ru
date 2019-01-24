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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6576dc19ed092ca12846a9780236e041daa64956
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727135"
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="a77ea-102">Структура COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="a77ea-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="a77ea-103">Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="a77ea-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a77ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a77ea-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="a77ea-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a77ea-105">Members</span></span>  
  
|<span data-ttu-id="a77ea-106">Член</span><span class="sxs-lookup"><span data-stu-id="a77ea-106">Member</span></span>|<span data-ttu-id="a77ea-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a77ea-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="a77ea-108">Значение [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) перечисление, указывающее тип предложения исключения только что введенный код или влево.</span><span class="sxs-lookup"><span data-stu-id="a77ea-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="a77ea-109">Точка входа собственного обработчика условий — например, содержимое регистра X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="a77ea-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="a77ea-110">Указатель на логический кадр обработчика условий — например, содержимое регистра X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="a77ea-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="a77ea-111">Указатель на теневой стек.</span><span class="sxs-lookup"><span data-stu-id="a77ea-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="a77ea-112">Это значение представляет собой содержание регистра BSP и применяется только к IA64.</span><span class="sxs-lookup"><span data-stu-id="a77ea-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a77ea-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a77ea-113">Remarks</span></span>  
 <span data-ttu-id="a77ea-114">Получив уведомление об исключении, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) можно использовать для получения собственного кадре и адрес сведений о предложении исключение (`catch` / `finally`/filter), будет выполняться или только что запущенного.</span><span class="sxs-lookup"><span data-stu-id="a77ea-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="a77ea-115">Выполнение условия исключения включает в себя эти обратные вызовы из общеязыковой среды выполнения (CLR):</span><span class="sxs-lookup"><span data-stu-id="a77ea-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="a77ea-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="a77ea-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="a77ea-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="a77ea-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="a77ea-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="a77ea-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="a77ea-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="a77ea-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="a77ea-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="a77ea-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="a77ea-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="a77ea-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="a77ea-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a77ea-122">Requirements</span></span>  
 <span data-ttu-id="a77ea-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a77ea-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a77ea-124">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a77ea-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a77ea-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a77ea-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a77ea-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a77ea-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77ea-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a77ea-127">See also</span></span>
- [<span data-ttu-id="a77ea-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="a77ea-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
