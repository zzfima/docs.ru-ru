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
ms.openlocfilehash: bb00a56b0d80b78867f70e64c1c9bdf0fc49e1be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178403"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="78aa8-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="78aa8-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="78aa8-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="78aa8-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78aa8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78aa8-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="78aa8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78aa8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="78aa8-106">[in] Идентификатор модуля, который вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="78aa8-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78aa8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="78aa8-107">Remarks</span></span>  
 <span data-ttu-id="78aa8-108">Значение `moduleId` не является допустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это последняя возможность профилировщика для получения сведений об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="78aa8-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78aa8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="78aa8-109">Requirements</span></span>  
 <span data-ttu-id="78aa8-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78aa8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78aa8-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78aa8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78aa8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78aa8-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="78aa8-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="78aa8-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78aa8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="78aa8-114">See also</span></span>

- [<span data-ttu-id="78aa8-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="78aa8-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="78aa8-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="78aa8-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
