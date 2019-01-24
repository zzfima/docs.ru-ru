---
title: Метод ICorProfilerCallback::ModuleLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d15656079c087026a905d9268edf4966d8ef4034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503564"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="3f019-102">Метод ICorProfilerCallback::ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="3f019-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="3f019-103">Уведомляет профилировщик об окончании загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="3f019-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f019-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f019-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f019-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f019-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3f019-106">[in] Идентификатор модуля, загрузка завершена.</span><span class="sxs-lookup"><span data-stu-id="3f019-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3f019-107">[in] Значение HRESULT, указывающее, был ли модуль загружен успешно.</span><span class="sxs-lookup"><span data-stu-id="3f019-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f019-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f019-108">Remarks</span></span>  
 <span data-ttu-id="3f019-109">Значение `moduleId` не является допустимым для информационного запроса до `ModuleLoadFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="3f019-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="3f019-110">Загрузка модуля некоторых частей может по-прежнему после `ModuleLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3f019-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="3f019-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="3f019-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3f019-112">Тем не менее значение HRESULT в `hrStatus` указывает только что первая часть загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="3f019-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f019-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3f019-113">Requirements</span></span>  
 <span data-ttu-id="3f019-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f019-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f019-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f019-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f019-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f019-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f019-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f019-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f019-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3f019-118">See also</span></span>
- [<span data-ttu-id="3f019-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3f019-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3f019-120">Метод ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="3f019-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
