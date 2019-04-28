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
ms.openlocfilehash: 3503aa1eb86246365e31f52313893ad8713f5748
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992190"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="206b0-102">Метод ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="206b0-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="206b0-103">Уведомляет профилировщик о загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="206b0-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="206b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="206b0-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="206b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="206b0-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="206b0-106">[in] Идентификатор модуля, который загружается.</span><span class="sxs-lookup"><span data-stu-id="206b0-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="206b0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="206b0-107">Remarks</span></span>  
 <span data-ttu-id="206b0-108">Значение `moduleId` не является допустимым для информационного запроса до [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="206b0-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="206b0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="206b0-109">Requirements</span></span>  
 <span data-ttu-id="206b0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="206b0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="206b0-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="206b0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="206b0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="206b0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="206b0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="206b0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="206b0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="206b0-114">See also</span></span>

- [<span data-ttu-id="206b0-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="206b0-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
