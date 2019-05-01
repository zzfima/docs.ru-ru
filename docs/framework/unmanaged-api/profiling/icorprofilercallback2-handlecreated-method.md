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
ms.openlocfilehash: 5cd8b08c630d56ca3b59cad768e285b630d64e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049771"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="0515e-102">Метод ICorProfilerCallback2::HandleCreated</span><span class="sxs-lookup"><span data-stu-id="0515e-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="0515e-103">Уведомляет профилировщик кода о том, что был создан дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0515e-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0515e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0515e-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0515e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0515e-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="0515e-106">[in] Идентификатор дескриптора для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0515e-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="0515e-107">[in] Идентификатор объекта, для которого был создан обработчик сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0515e-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0515e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0515e-108">Requirements</span></span>  
 <span data-ttu-id="0515e-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0515e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0515e-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0515e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0515e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0515e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0515e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0515e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0515e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0515e-113">See also</span></span>

- [<span data-ttu-id="0515e-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0515e-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0515e-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="0515e-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
