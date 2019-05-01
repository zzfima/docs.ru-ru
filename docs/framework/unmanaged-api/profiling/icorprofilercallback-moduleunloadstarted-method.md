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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041942"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="ac514-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="ac514-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="ac514-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="ac514-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac514-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac514-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ac514-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac514-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ac514-106">[in] Идентификатор модуля, который вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="ac514-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac514-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac514-107">Remarks</span></span>  
 <span data-ttu-id="ac514-108">Значение `moduleId` не является допустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это последняя возможность профилировщика для получения сведений об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="ac514-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac514-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ac514-109">Requirements</span></span>  
 <span data-ttu-id="ac514-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac514-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac514-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac514-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac514-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac514-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac514-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac514-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac514-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ac514-114">See also</span></span>

- [<span data-ttu-id="ac514-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ac514-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ac514-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="ac514-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
