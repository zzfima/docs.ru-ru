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
ms.openlocfilehash: fcfdddbd5316c098754ea7b0d4714b050c64fe55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175152"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="8b799-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="8b799-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="8b799-103">Уведомляет профайлера о том, что модуль выгружается.</span><span class="sxs-lookup"><span data-stu-id="8b799-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b799-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b799-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="8b799-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b799-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8b799-106">(в) Идентификатор разгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="8b799-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b799-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b799-107">Remarks</span></span>  
 <span data-ttu-id="8b799-108">Значение не `moduleId` является действительным для запроса информации после возврата `ModuleUnloadStarted` метода - это последний шанс профайлера получить информацию об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="8b799-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b799-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8b799-109">Requirements</span></span>  
 <span data-ttu-id="8b799-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b799-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b799-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b799-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b799-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b799-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b799-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b799-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b799-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8b799-114">See also</span></span>

- [<span data-ttu-id="8b799-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8b799-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8b799-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="8b799-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
