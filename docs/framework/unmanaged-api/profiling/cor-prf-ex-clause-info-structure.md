---
title: "Структура COR_PRF_EX_CLAUSE_INFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_EX_CLAUSE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords: COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65025384aa94ac363336bae7f37f8ea88a3bab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="c0734-102">Структура COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="c0734-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="c0734-103">Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="c0734-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0734-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0734-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c0734-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c0734-105">Members</span></span>  
  
|<span data-ttu-id="c0734-106">Член</span><span class="sxs-lookup"><span data-stu-id="c0734-106">Member</span></span>|<span data-ttu-id="c0734-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0734-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="c0734-108">Значение [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) перечисления, которое указывает тип предложения исключения кода, который только что введен или удален.</span><span class="sxs-lookup"><span data-stu-id="c0734-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="c0734-109">Точка входа в машинный код обработчика условий — например, содержимое регистра X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="c0734-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="c0734-110">Указатель на логический кадр обработчика условий — например, содержимое регистра X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="c0734-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="c0734-111">Указатель на теневой стек.</span><span class="sxs-lookup"><span data-stu-id="c0734-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="c0734-112">Это значение является содержимым регистра BSP и применяется только к IA64.</span><span class="sxs-lookup"><span data-stu-id="c0734-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0734-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0734-113">Remarks</span></span>  
 <span data-ttu-id="c0734-114">Получив уведомление об исключении, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) можно использовать для получения собственного сведения о кадре и адрес для предложения исключения (`catch` / `finally`/filter), будет выполняться, или только что запущенного.</span><span class="sxs-lookup"><span data-stu-id="c0734-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="c0734-115">Выполнение условия исключения включает в себя эти обратные вызовы из общеязыковой среды выполнения (CLR):</span><span class="sxs-lookup"><span data-stu-id="c0734-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="c0734-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="c0734-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="c0734-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="c0734-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="c0734-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="c0734-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="c0734-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="c0734-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="c0734-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="c0734-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="c0734-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="c0734-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="c0734-122">Требования</span><span class="sxs-lookup"><span data-stu-id="c0734-122">Requirements</span></span>  
 <span data-ttu-id="c0734-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0734-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0734-124">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c0734-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c0734-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0734-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0734-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0734-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0734-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c0734-127">See Also</span></span>  
 [<span data-ttu-id="c0734-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="c0734-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
