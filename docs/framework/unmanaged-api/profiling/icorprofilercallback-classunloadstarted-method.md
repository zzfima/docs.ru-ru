---
title: Метод ICorProfilerCallback::ClassUnloadStarted
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c30fb5d5576a7bed403f48504ead923df212de9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="7899d-102">Метод ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="7899d-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="7899d-103">Уведомляет профилировщик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="7899d-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7899d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7899d-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7899d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7899d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7899d-106">[in] Идентифицирует класс, выгружается.</span><span class="sxs-lookup"><span data-stu-id="7899d-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7899d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7899d-107">Remarks</span></span>  
 <span data-ttu-id="7899d-108">Значение `classId` является недопустимым для информационного запроса после `ClassUnloadStarted` возвращает метод — это профилировщика последнюю возможность получить сведения об этом классе.</span><span class="sxs-lookup"><span data-stu-id="7899d-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7899d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7899d-109">Requirements</span></span>  
 <span data-ttu-id="7899d-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7899d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7899d-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7899d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7899d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7899d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7899d-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7899d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7899d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7899d-114">See Also</span></span>  
 [<span data-ttu-id="7899d-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7899d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="7899d-116">Метод ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="7899d-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
