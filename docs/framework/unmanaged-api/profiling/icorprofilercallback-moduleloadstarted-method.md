---
title: Метод ICorProfilerCallback::ModuleLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b847cbbdf1bfccd91ca212dadd1fcd82cc12c82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768196"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="3253c-102">Метод ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="3253c-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="3253c-103">Уведомляет профилировщик о загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="3253c-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3253c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3253c-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3253c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3253c-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3253c-106">[in] Идентификатор модуля, который загружается.</span><span class="sxs-lookup"><span data-stu-id="3253c-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3253c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3253c-107">Remarks</span></span>  
 <span data-ttu-id="3253c-108">Значение `moduleId` не является допустимым для информационного запроса до [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="3253c-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3253c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3253c-109">Requirements</span></span>  
 <span data-ttu-id="3253c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3253c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3253c-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3253c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3253c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3253c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3253c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3253c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3253c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3253c-114">See also</span></span>

- [<span data-ttu-id="3253c-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3253c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
