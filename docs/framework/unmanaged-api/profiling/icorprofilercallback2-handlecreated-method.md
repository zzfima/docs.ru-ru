---
title: Метод ICorProfilerCallback2::HandleCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 47654d7ad1803e57f5db846ea0370d1f736deaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="97275-102">Метод ICorProfilerCallback2::HandleCreated</span><span class="sxs-lookup"><span data-stu-id="97275-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="97275-103">Уведомляет профилировщик кода, что был создан дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="97275-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97275-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97275-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97275-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97275-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="97275-106">[in] Идентификатор дескриптора для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="97275-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="97275-107">[in] Идентификатор объекта, для которого был создан обработчик сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="97275-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97275-108">Требования</span><span class="sxs-lookup"><span data-stu-id="97275-108">Requirements</span></span>  
 <span data-ttu-id="97275-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97275-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97275-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97275-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97275-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97275-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97275-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97275-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97275-113">См. также</span><span class="sxs-lookup"><span data-stu-id="97275-113">See Also</span></span>  
 [<span data-ttu-id="97275-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="97275-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="97275-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="97275-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
