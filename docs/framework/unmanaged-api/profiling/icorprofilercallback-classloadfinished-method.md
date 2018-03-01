---
title: "Метод ICorProfilerCallback::ClassLoadFinished"
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
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae55325f514f9bec3efdf4764958e4b3fafd922b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="efeb3-102">Метод ICorProfilerCallback::ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="efeb3-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="efeb3-103">Уведомляет профилировщик об окончании загрузки класса.</span><span class="sxs-lookup"><span data-stu-id="efeb3-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efeb3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efeb3-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efeb3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efeb3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="efeb3-106">[in] Идентифицирует класс, который был загружен.</span><span class="sxs-lookup"><span data-stu-id="efeb3-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="efeb3-107">[in] Значение HRESULT, указывающее, успешно загрузить класс.</span><span class="sxs-lookup"><span data-stu-id="efeb3-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efeb3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="efeb3-108">Remarks</span></span>  
 <span data-ttu-id="efeb3-109">Значение `classId` является недопустимым для информационного запроса до `ClassLoadFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="efeb3-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="efeb3-110">Некоторые части при загрузке класса может быть продолжено после `ClassLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="efeb3-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="efeb3-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="efeb3-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="efeb3-112">Тем не менее значение HRESULT в `hrStatus` указывает только на том, что в первой части при загрузке класса.</span><span class="sxs-lookup"><span data-stu-id="efeb3-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efeb3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="efeb3-113">Requirements</span></span>  
 <span data-ttu-id="efeb3-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efeb3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efeb3-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efeb3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="efeb3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efeb3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efeb3-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efeb3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efeb3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="efeb3-118">See Also</span></span>  
 [<span data-ttu-id="efeb3-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="efeb3-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="efeb3-120">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="efeb3-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
