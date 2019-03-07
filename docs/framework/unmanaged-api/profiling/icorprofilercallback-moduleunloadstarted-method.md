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
ms.openlocfilehash: 2ebeaaa88f3c7320f38d33a9c027d5aa76bf9673
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495875"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="60c0b-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="60c0b-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="60c0b-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="60c0b-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60c0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60c0b-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="60c0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="60c0b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="60c0b-106">[in] Идентификатор модуля, который вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="60c0b-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60c0b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="60c0b-107">Remarks</span></span>  
 <span data-ttu-id="60c0b-108">Значение `moduleId` не является допустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это последняя возможность профилировщика для получения сведений об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="60c0b-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60c0b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="60c0b-109">Requirements</span></span>  
 <span data-ttu-id="60c0b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60c0b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60c0b-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60c0b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60c0b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60c0b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60c0b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c0b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c0b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="60c0b-114">See also</span></span>
- [<span data-ttu-id="60c0b-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="60c0b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="60c0b-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="60c0b-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
