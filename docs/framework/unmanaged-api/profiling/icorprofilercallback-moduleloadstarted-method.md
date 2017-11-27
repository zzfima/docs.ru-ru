---
title: "Метод ICorProfilerCallback::ModuleLoadStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad525b44169a85e61140c9e2a8d83c967945b2f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="7694c-102">Метод ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="7694c-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="7694c-103">Уведомляет профилировщик о том, что при загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="7694c-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7694c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7694c-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7694c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7694c-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="7694c-106">[in] Идентификатор модуля, загружается.</span><span class="sxs-lookup"><span data-stu-id="7694c-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7694c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7694c-107">Remarks</span></span>  
 <span data-ttu-id="7694c-108">Значение `moduleId` является недопустимым для информационного запроса до [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="7694c-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7694c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7694c-109">Requirements</span></span>  
 <span data-ttu-id="7694c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7694c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7694c-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7694c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7694c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7694c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7694c-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7694c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7694c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7694c-114">See Also</span></span>  
 [<span data-ttu-id="7694c-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7694c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
