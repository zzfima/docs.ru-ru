---
title: "Метод ICorProfilerCallback::ClassUnloadStarted"
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
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 994fe840f728b244e5a6e6c83c03340961c30413
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="cea40-102">Метод ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="cea40-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="cea40-103">Уведомляет профилировщик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="cea40-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cea40-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cea40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cea40-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cea40-106">[in] Идентифицирует класс, выгружается.</span><span class="sxs-lookup"><span data-stu-id="cea40-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cea40-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cea40-107">Remarks</span></span>  
 <span data-ttu-id="cea40-108">Значение `classId` является недопустимым для информационного запроса после `ClassUnloadStarted` возвращает метод — это профилировщика последнюю возможность получить сведения об этом классе.</span><span class="sxs-lookup"><span data-stu-id="cea40-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cea40-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cea40-109">Requirements</span></span>  
 <span data-ttu-id="cea40-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cea40-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea40-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cea40-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cea40-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cea40-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cea40-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea40-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea40-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cea40-114">See Also</span></span>  
 [<span data-ttu-id="cea40-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cea40-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="cea40-116">Метод ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="cea40-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
