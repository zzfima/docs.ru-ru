---
title: Метод ICorProfilerInfo::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f26fd93d42a709249936815d3c29ae572482f427
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992047"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="5c298-102">Метод ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="5c298-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="5c298-103">Получает идентификатор контекста ассоциированы с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="5c298-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c298-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c298-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c298-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c298-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5c298-106">[in] Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="5c298-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="5c298-107">[out] Указатель на идентификатор контекста ассоциированы с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="5c298-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="5c298-108">Если поток не имеет контекста ассоциированы с ним, эта функция возвращает CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="5c298-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c298-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5c298-109">Requirements</span></span>  
 <span data-ttu-id="5c298-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c298-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c298-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c298-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c298-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c298-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c298-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c298-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c298-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5c298-114">See also</span></span>

- [<span data-ttu-id="5c298-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5c298-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
