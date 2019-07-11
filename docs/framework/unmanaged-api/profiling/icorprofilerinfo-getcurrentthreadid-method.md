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
ms.openlocfilehash: db5ed871734205d59c602cc8b5c0cc9e8ac4682a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762872"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="b8ee8-102">Метод ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="b8ee8-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="b8ee8-103">Получает идентификатор текущего потока, в случае управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="b8ee8-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ee8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8ee8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8ee8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8ee8-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="b8ee8-106">[out] Указатель на возвращенный идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="b8ee8-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8ee8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8ee8-107">Remarks</span></span>  
 <span data-ttu-id="b8ee8-108">Если текущий поток находится в потоке внутренней среды выполнения или других неуправляемый поток `GetCurrentThreadID` возвращает значение HRESULT и возвращаемым значением CORPROF_E_NOT_MANAGED_THREAD `pThreadId` параметр будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="b8ee8-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ee8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b8ee8-109">Requirements</span></span>  
 <span data-ttu-id="b8ee8-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ee8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ee8-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8ee8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8ee8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8ee8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8ee8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ee8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ee8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b8ee8-114">See also</span></span>

- [<span data-ttu-id="b8ee8-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b8ee8-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
