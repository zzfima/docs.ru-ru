---
title: Метод ICorProfilerCallback::FunctionUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: 988843559e55cc4cacd2a40bb3e6ac51721e99b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175165"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="13db2-102">Метод ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="13db2-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="13db2-103">Уведомляет профайлера о том, что время выполнения начало выгружать функцию.</span><span class="sxs-lookup"><span data-stu-id="13db2-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13db2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13db2-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="13db2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13db2-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="13db2-106">\[идентификатор функции, которая разгружается.</span><span class="sxs-lookup"><span data-stu-id="13db2-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="13db2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="13db2-107">Remarks</span></span>  
 <span data-ttu-id="13db2-108">Значение `functionId` параметра больше не действует после того, как этот метод возвращается к вызывающему.</span><span class="sxs-lookup"><span data-stu-id="13db2-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13db2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="13db2-109">Requirements</span></span>  
 <span data-ttu-id="13db2-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13db2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13db2-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13db2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13db2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13db2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13db2-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13db2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13db2-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13db2-114">See also</span></span>

- [<span data-ttu-id="13db2-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="13db2-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
