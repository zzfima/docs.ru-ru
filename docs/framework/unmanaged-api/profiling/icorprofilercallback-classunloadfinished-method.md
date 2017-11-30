---
title: "Метод ICorProfilerCallback::ClassUnloadFinished"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 920fa36edcc49c12f8f73644cc4e6551a0e954ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="c121f-102">Метод ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="c121f-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="c121f-103">Уведомляет профилировщик о завершении выгрузки класса.</span><span class="sxs-lookup"><span data-stu-id="c121f-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c121f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c121f-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c121f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c121f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c121f-106">[in] Идентифицирует класс, который был выгружен.</span><span class="sxs-lookup"><span data-stu-id="c121f-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c121f-107">[in] Значение HRESULT, указывающее, является ли класс выгружено успешно.</span><span class="sxs-lookup"><span data-stu-id="c121f-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c121f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c121f-108">Remarks</span></span>  
 <span data-ttu-id="c121f-109">Некоторые части выгрузки класса может быть продолжено после `ClassUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c121f-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="c121f-110">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="c121f-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c121f-111">Тем не менее значение HRESULT в `hrStatus` указывает только на том, что в первой части выгрузки класса.</span><span class="sxs-lookup"><span data-stu-id="c121f-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c121f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c121f-112">Requirements</span></span>  
 <span data-ttu-id="c121f-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c121f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c121f-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c121f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c121f-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c121f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c121f-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c121f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c121f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c121f-117">See Also</span></span>  
 [<span data-ttu-id="c121f-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c121f-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c121f-119">Метод ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="c121f-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
