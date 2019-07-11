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
ms.openlocfilehash: c99ddc66cca0a0d0083cfa19cfca34a1e557d4e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769145"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="64598-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="64598-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="64598-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="64598-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64598-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64598-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="64598-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64598-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="64598-106">[in] Идентификатор модуля, который вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="64598-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64598-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="64598-107">Remarks</span></span>  
 <span data-ttu-id="64598-108">Значение `moduleId` не является допустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это последняя возможность профилировщика для получения сведений об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="64598-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64598-109">Требования</span><span class="sxs-lookup"><span data-stu-id="64598-109">Requirements</span></span>  
 <span data-ttu-id="64598-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64598-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64598-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64598-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64598-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64598-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64598-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64598-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64598-114">См. также</span><span class="sxs-lookup"><span data-stu-id="64598-114">See also</span></span>

- [<span data-ttu-id="64598-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="64598-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="64598-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="64598-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
