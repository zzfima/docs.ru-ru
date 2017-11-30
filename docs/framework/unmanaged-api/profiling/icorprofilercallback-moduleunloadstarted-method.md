---
title: "Метод ICorProfilerCallback::ModuleUnloadStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 069e47ad3d1dd9459b7344b1af1a2ad6d32305ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="f8843-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="f8843-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="f8843-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="f8843-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8843-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8843-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8843-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8843-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f8843-106">[in] Идентификатор модуля, выгружается.</span><span class="sxs-lookup"><span data-stu-id="f8843-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8843-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8843-107">Remarks</span></span>  
 <span data-ttu-id="f8843-108">Значение `moduleId` является недопустимым для информационного запроса после `ModuleUnloadStarted` возвращает метод — это профилировщика последнюю возможность получить сведения об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="f8843-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8843-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f8843-109">Requirements</span></span>  
 <span data-ttu-id="f8843-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8843-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8843-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8843-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8843-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8843-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8843-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8843-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8843-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f8843-114">See Also</span></span>  
 [<span data-ttu-id="f8843-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f8843-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f8843-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="f8843-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
