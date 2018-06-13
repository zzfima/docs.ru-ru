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
ms.openlocfilehash: e9d6c322d82b34af908065106ef03ccf5ff846e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451734"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="a6c80-102">Метод ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="a6c80-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="a6c80-103">Уведомляет профилировщик о том, что при загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="a6c80-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6c80-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6c80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6c80-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a6c80-106">[in] Идентификатор модуля, загружается.</span><span class="sxs-lookup"><span data-stu-id="a6c80-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6c80-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6c80-107">Remarks</span></span>  
 <span data-ttu-id="a6c80-108">Значение `moduleId` является недопустимым для информационного запроса до [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="a6c80-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6c80-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a6c80-109">Requirements</span></span>  
 <span data-ttu-id="a6c80-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6c80-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6c80-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6c80-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6c80-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6c80-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6c80-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6c80-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c80-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a6c80-114">See Also</span></span>  
 [<span data-ttu-id="a6c80-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a6c80-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
