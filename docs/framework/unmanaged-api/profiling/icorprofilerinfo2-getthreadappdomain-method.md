---
title: Метод ICorProfilerInfo2::GetThreadAppDomain
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
ms.openlocfilehash: 7c1ee1c39fbf2dcc1f16df3bc94a235676a216dd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862572"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="b43ff-102">Метод ICorProfilerInfo2::GetThreadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b43ff-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="b43ff-103">Возвращает идентификатор домена приложения, в котором указанный поток в настоящий момент исполняет код.</span><span class="sxs-lookup"><span data-stu-id="b43ff-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b43ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b43ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b43ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b43ff-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b43ff-106">окне Идентификатор, указывающий поток.</span><span class="sxs-lookup"><span data-stu-id="b43ff-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="b43ff-107">заполняет Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b43ff-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b43ff-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b43ff-108">Requirements</span></span>  
 <span data-ttu-id="b43ff-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b43ff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b43ff-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b43ff-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b43ff-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b43ff-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b43ff-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b43ff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43ff-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="b43ff-113">See also</span></span>

- [<span data-ttu-id="b43ff-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b43ff-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b43ff-115">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b43ff-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
