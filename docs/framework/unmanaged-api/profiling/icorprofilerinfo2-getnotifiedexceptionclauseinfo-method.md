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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cabe2f1ad5b586fed24c7317bb3a7b8407e09158
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167015"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="d614f-102">Метод ICorProfilerInfo2::GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="d614f-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="d614f-103">Возвращает собственные сведения о кадре и адрес для условия исключения (`catch`/`finally`/`filter`), будет выполняться или только что запущенного.</span><span class="sxs-lookup"><span data-stu-id="d614f-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d614f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d614f-104">Syntax</span></span>  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d614f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d614f-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="d614f-106">[out] Указатель на [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) структура, описывающая текущий экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="d614f-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d614f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d614f-107">Remarks</span></span>  
 <span data-ttu-id="d614f-108">Получив уведомление об исключении, `GetNotifiedExceptionClauseInfo` можно использовать для получения собственного кадре и адрес сведений о предложении исключение (`catch`/`finally`/`filter`), будет выполняться ([ ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), или [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)получения профилировщиком обратного вызова) или просто запустить ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), или [ ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) получения профилировщиком обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="d614f-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="d614f-109">Этот вызов может быть выполнен в любое время после одного из выше обратных вызовов Enter пока соответствующий обратного вызова Leave или вложенное исключение возникает в текущем предложении, в котором случае выдается никакого уведомления оставьте этого предложения.</span><span class="sxs-lookup"><span data-stu-id="d614f-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="d614f-110">Обратите внимание на то, что он не поддерживается для созданного исключения для экранирования `filter` предложения исключения, так что всегда уведомление оставьте в этом случае.</span><span class="sxs-lookup"><span data-stu-id="d614f-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d614f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d614f-111">Requirements</span></span>  
 <span data-ttu-id="d614f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d614f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d614f-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d614f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d614f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d614f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d614f-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d614f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d614f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d614f-116">See also</span></span>

- [<span data-ttu-id="d614f-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d614f-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="d614f-118">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="d614f-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
