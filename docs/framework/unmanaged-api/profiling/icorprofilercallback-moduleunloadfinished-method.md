---
title: Метод ICorProfilerCallback::ModuleUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f096c1f3898348141e13da44f39f2768417acd1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042088"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="9ded8-102">Метод ICorProfilerCallback::ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="9ded8-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="9ded8-103">Уведомляет профилировщик о завершении выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="9ded8-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ded8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ded8-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ded8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ded8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9ded8-106">[in] Идентификатор модуля, который был выгружен.</span><span class="sxs-lookup"><span data-stu-id="9ded8-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9ded8-107">[in] Значение HRESULT, указывающее, является ли модуль был успешно высвобожден.</span><span class="sxs-lookup"><span data-stu-id="9ded8-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ded8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ded8-108">Remarks</span></span>  
 <span data-ttu-id="9ded8-109">Значение `moduleId` не является допустимым для информационного запроса после [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) возвращает метод.</span><span class="sxs-lookup"><span data-stu-id="9ded8-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="9ded8-110">Некоторые части выгрузки класса может по-прежнему после `ModuleUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="9ded8-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="9ded8-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="9ded8-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9ded8-112">Тем не менее значение HRESULT в `hrStatus` указывает только что в первой части выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="9ded8-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ded8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9ded8-113">Requirements</span></span>  
 <span data-ttu-id="9ded8-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ded8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ded8-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ded8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ded8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ded8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ded8-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ded8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ded8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9ded8-118">See also</span></span>

- [<span data-ttu-id="9ded8-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9ded8-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
