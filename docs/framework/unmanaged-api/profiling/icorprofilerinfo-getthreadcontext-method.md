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
ms.openlocfilehash: f8eff85392d355ea54980ac6b29e3c4cebb1b240
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869600"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="0d572-102">Метод ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="0d572-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="0d572-103">Возвращает удостоверение контекста, которое в настоящее время связано с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="0d572-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d572-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d572-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d572-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d572-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0d572-106">окне Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="0d572-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="0d572-107">заполняет Указатель на идентификатор контекста, который в настоящее время связан с указанным потоком.</span><span class="sxs-lookup"><span data-stu-id="0d572-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="0d572-108">Если с потоком не связан ни один контекст, эта функция возвратит CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="0d572-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d572-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0d572-109">Requirements</span></span>  
 <span data-ttu-id="0d572-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d572-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d572-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d572-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d572-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d572-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d572-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d572-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d572-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d572-114">See also</span></span>

- [<span data-ttu-id="0d572-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0d572-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
