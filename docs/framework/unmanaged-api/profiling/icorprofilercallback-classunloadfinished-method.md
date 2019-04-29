---
title: Метод ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d01f3d7485b19c076d9cd3e83aeccbcf5e728f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597984"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="622af-102">Метод ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="622af-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="622af-103">Уведомляет профилировщик о завершении выгрузки класса.</span><span class="sxs-lookup"><span data-stu-id="622af-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="622af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="622af-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="622af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="622af-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="622af-106">[in] Идентифицирует класс, который был выгружен.</span><span class="sxs-lookup"><span data-stu-id="622af-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="622af-107">[in] Значение HRESULT, указывающее, является ли класс был успешно высвобожден.</span><span class="sxs-lookup"><span data-stu-id="622af-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="622af-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="622af-108">Remarks</span></span>  
 <span data-ttu-id="622af-109">Некоторые части выгрузки класса может по-прежнему после `ClassUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="622af-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="622af-110">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="622af-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="622af-111">Тем не менее значение HRESULT в `hrStatus` указывает, что в первой части выгрузки класса выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="622af-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="622af-112">Требования</span><span class="sxs-lookup"><span data-stu-id="622af-112">Requirements</span></span>  
 <span data-ttu-id="622af-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="622af-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="622af-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="622af-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="622af-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="622af-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="622af-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="622af-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622af-117">См. также</span><span class="sxs-lookup"><span data-stu-id="622af-117">See also</span></span>

- [<span data-ttu-id="622af-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="622af-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="622af-119">Метод ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="622af-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
