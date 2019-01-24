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
ms.openlocfilehash: 9bb7e31f3bff9bfc2cb44259f29b6a7293193371
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623218"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="e4154-102">Метод ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="e4154-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="e4154-103">Уведомляет профилировщик о завершении выгрузки класса.</span><span class="sxs-lookup"><span data-stu-id="e4154-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4154-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4154-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4154-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4154-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e4154-106">[in] Идентифицирует класс, который был выгружен.</span><span class="sxs-lookup"><span data-stu-id="e4154-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e4154-107">[in] Значение HRESULT, указывающее, является ли класс был успешно высвобожден.</span><span class="sxs-lookup"><span data-stu-id="e4154-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4154-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4154-108">Remarks</span></span>  
 <span data-ttu-id="e4154-109">Некоторые части выгрузки класса может по-прежнему после `ClassUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e4154-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="e4154-110">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="e4154-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e4154-111">Тем не менее значение HRESULT в `hrStatus` указывает, что в первой части выгрузки класса выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="e4154-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4154-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e4154-112">Requirements</span></span>  
 <span data-ttu-id="e4154-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4154-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4154-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4154-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4154-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4154-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4154-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4154-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4154-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e4154-117">See also</span></span>
- [<span data-ttu-id="e4154-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e4154-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e4154-119">Метод ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="e4154-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
