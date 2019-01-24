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
ms.openlocfilehash: 8be698d27ce69f955e5c1f17f5258602880c4021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618702"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="943e8-102">Метод ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="943e8-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="943e8-103">Получает идентификатор текущего потока, в случае управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="943e8-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="943e8-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="943e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="943e8-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="943e8-106">[out] Указатель на возвращенный идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="943e8-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="943e8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="943e8-107">Remarks</span></span>  
 <span data-ttu-id="943e8-108">Если текущий поток находится в потоке внутренней среды выполнения или других неуправляемый поток `GetCurrentThreadID` возвращает значение HRESULT и возвращаемым значением CORPROF_E_NOT_MANAGED_THREAD `pThreadId` параметр будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="943e8-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943e8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="943e8-109">Requirements</span></span>  
 <span data-ttu-id="943e8-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943e8-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="943e8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="943e8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="943e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="943e8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943e8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="943e8-114">See also</span></span>
- [<span data-ttu-id="943e8-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="943e8-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
