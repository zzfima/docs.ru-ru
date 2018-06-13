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
ms.openlocfilehash: acb4d67f41b1434fe8052a74e976907f24fecd31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453581"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="ff2f6-102">Метод ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="ff2f6-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="ff2f6-103">Возвращает идентификатор контекста, в текущий момент связан с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="ff2f6-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff2f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff2f6-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff2f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff2f6-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ff2f6-106">[in] Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="ff2f6-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="ff2f6-107">[out] Указатель на идентификатор контекста, в текущий момент связан с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="ff2f6-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="ff2f6-108">Если поток не имеет контекста в данный момент связанный с ним, эта функция возвращает CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="ff2f6-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff2f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ff2f6-109">Requirements</span></span>  
 <span data-ttu-id="ff2f6-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff2f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff2f6-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff2f6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff2f6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff2f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff2f6-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff2f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2f6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ff2f6-114">See Also</span></span>  
 [<span data-ttu-id="ff2f6-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ff2f6-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
