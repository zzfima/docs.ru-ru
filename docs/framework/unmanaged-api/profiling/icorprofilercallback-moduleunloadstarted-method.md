---
title: Метод ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c509606995a0ddb00a8b586ce8b8cd54b7694cd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452514"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="2be95-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="2be95-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="2be95-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="2be95-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2be95-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="2be95-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2be95-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2be95-106">[in] Идентификатор модуля, выгружается.</span><span class="sxs-lookup"><span data-stu-id="2be95-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2be95-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2be95-107">Remarks</span></span>  
 <span data-ttu-id="2be95-108">Значение `moduleId` является недопустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это профилировщика последнюю возможность получить сведения об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="2be95-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be95-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2be95-109">Requirements</span></span>  
 <span data-ttu-id="2be95-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2be95-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be95-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2be95-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2be95-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2be95-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2be95-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2be95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be95-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2be95-114">See Also</span></span>  
 [<span data-ttu-id="2be95-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2be95-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="2be95-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="2be95-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
