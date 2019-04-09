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
ms.openlocfilehash: 802072f3a0151aabc5ca5796df57ea7c694a2070
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179040"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="55027-102">Метод ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="55027-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="55027-103">Получает идентификатор текущего потока, в случае управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="55027-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55027-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55027-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55027-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55027-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="55027-106">[out] Указатель на возвращенный идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="55027-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55027-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="55027-107">Remarks</span></span>  
 <span data-ttu-id="55027-108">Если текущий поток находится в потоке внутренней среды выполнения или других неуправляемый поток `GetCurrentThreadID` возвращает значение HRESULT и возвращаемым значением CORPROF_E_NOT_MANAGED_THREAD `pThreadId` параметр будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="55027-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55027-109">Требования</span><span class="sxs-lookup"><span data-stu-id="55027-109">Requirements</span></span>  
 <span data-ttu-id="55027-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55027-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55027-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55027-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55027-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55027-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="55027-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="55027-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55027-114">См. также</span><span class="sxs-lookup"><span data-stu-id="55027-114">See also</span></span>

- [<span data-ttu-id="55027-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="55027-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
