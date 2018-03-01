---
title: "Метод ICorProfilerCallback::ModuleUnloadStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 384d655254cc79283f93ff2e608b0429c4a84ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="4ee10-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="4ee10-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="4ee10-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="4ee10-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ee10-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ee10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ee10-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4ee10-106">[in] Идентификатор модуля, выгружается.</span><span class="sxs-lookup"><span data-stu-id="4ee10-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ee10-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ee10-107">Remarks</span></span>  
 <span data-ttu-id="4ee10-108">Значение `moduleId` является недопустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это профилировщика последнюю возможность получить сведения об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="4ee10-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ee10-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4ee10-109">Requirements</span></span>  
 <span data-ttu-id="4ee10-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ee10-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ee10-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ee10-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ee10-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ee10-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ee10-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ee10-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee10-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4ee10-114">See Also</span></span>  
 [<span data-ttu-id="4ee10-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4ee10-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4ee10-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="4ee10-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
