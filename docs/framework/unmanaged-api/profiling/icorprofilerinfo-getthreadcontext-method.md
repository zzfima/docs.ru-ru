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
ms.openlocfilehash: bc4643f1c90b3ea4d3b561249a4e76ff304737bd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438761"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="e4ee1-102">Метод ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="e4ee1-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="e4ee1-103">Возвращает удостоверение контекста, которое в настоящее время связано с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="e4ee1-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ee1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4ee1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4ee1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4ee1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e4ee1-106">окне Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="e4ee1-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="e4ee1-107">заполняет Указатель на идентификатор контекста, который в настоящее время связан с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="e4ee1-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="e4ee1-108">Если с потоком не связан ни один контекст, эта функция возвратит CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="e4ee1-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4ee1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e4ee1-109">Requirements</span></span>  
 <span data-ttu-id="e4ee1-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4ee1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4ee1-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4ee1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4ee1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4ee1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4ee1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ee1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ee1-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="e4ee1-114">See also</span></span>

- [<span data-ttu-id="e4ee1-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e4ee1-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
