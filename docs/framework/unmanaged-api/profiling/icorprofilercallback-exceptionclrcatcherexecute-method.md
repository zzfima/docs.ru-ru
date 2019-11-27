---
title: Метод ICorProfilerCallback::ExceptionCLRCatcherExecute
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: 165981627337c562dd3721b7d93cb2027d0a0c37
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444939"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="e94a2-102">Метод ICorProfilerCallback::ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="e94a2-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="e94a2-103">Вызывается, когда блок `catch` для исключения выполняется в самой среде CLR.</span><span class="sxs-lookup"><span data-stu-id="e94a2-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="e94a2-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e94a2-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e94a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e94a2-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="e94a2-106">Требования</span><span class="sxs-lookup"><span data-stu-id="e94a2-106">Requirements</span></span>  
 <span data-ttu-id="e94a2-107">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e94a2-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e94a2-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e94a2-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e94a2-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e94a2-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e94a2-110">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e94a2-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94a2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e94a2-111">See also</span></span>

- [<span data-ttu-id="e94a2-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e94a2-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e94a2-113">Метод ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="e94a2-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
