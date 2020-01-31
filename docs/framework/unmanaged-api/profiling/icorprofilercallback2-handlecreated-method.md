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
ms.openlocfilehash: 0c25a5cad01ef0eb268e90c38bd24d638b6f8cc4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865770"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="05c01-102">Метод ICorProfilerCallback2::HandleCreated</span><span class="sxs-lookup"><span data-stu-id="05c01-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="05c01-103">Уведомляет профилировщик кода о создании обработчика сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="05c01-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05c01-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05c01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05c01-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="05c01-106">окне Идентификатор обработчика для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="05c01-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="05c01-107">окне Идентификатор объекта, для которого был создан маркер сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="05c01-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05c01-108">Требования</span><span class="sxs-lookup"><span data-stu-id="05c01-108">Requirements</span></span>  
 <span data-ttu-id="05c01-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05c01-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05c01-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05c01-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05c01-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05c01-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05c01-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c01-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c01-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="05c01-113">See also</span></span>

- [<span data-ttu-id="05c01-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="05c01-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="05c01-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="05c01-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
