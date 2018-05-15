---
title: Метод ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89f7ff2c213dc510268f9e6c802813a48e870d99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="cbbfd-102">Метод ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="cbbfd-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="cbbfd-103">Получает идентификатор текущего потока, если это управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="cbbfd-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbbfd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbbfd-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbbfd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbbfd-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="cbbfd-106">[out] Указатель на возвращаемый идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="cbbfd-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbbfd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbbfd-107">Remarks</span></span>  
 <span data-ttu-id="cbbfd-108">Если текущий поток является потоком внутренней среды выполнения или другой неуправляемый поток `GetCurrentThreadID` возвращает значение HRESULT и возвращаемым значением CORPROF_E_NOT_MANAGED_THREAD `pThreadId` параметр будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="cbbfd-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbbfd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cbbfd-109">Requirements</span></span>  
 <span data-ttu-id="cbbfd-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbbfd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbbfd-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cbbfd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cbbfd-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbbfd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbbfd-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbbfd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbfd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cbbfd-114">See Also</span></span>  
 [<span data-ttu-id="cbbfd-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cbbfd-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
