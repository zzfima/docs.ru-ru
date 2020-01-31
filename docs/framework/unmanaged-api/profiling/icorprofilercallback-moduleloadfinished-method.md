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
ms.openlocfilehash: 661229e5fbd5d106662f0e823a1753bd76c33311
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866173"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="7a415-102">Метод ICorProfilerCallback::ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="7a415-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="7a415-103">Уведомляет профилировщик о завершении загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="7a415-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a415-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a415-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a415-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a415-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="7a415-106">окне Идентификатор модуля, загрузка которого завершена.</span><span class="sxs-lookup"><span data-stu-id="7a415-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="7a415-107">окне Значение HRESULT, указывающее, успешно ли загружен модуль.</span><span class="sxs-lookup"><span data-stu-id="7a415-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a415-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="7a415-108">Remarks</span></span>  
 <span data-ttu-id="7a415-109">Значение `moduleId` недопустимо для информационного запроса, пока не будет вызван метод `ModuleLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="7a415-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="7a415-110">Некоторые части загрузки модуля могут продолжаться после обратного вызова `ModuleLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="7a415-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="7a415-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="7a415-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="7a415-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть загрузки модуля завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="7a415-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a415-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7a415-113">Requirements</span></span>  
 <span data-ttu-id="7a415-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a415-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a415-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a415-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a415-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a415-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a415-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a415-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a415-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a415-118">See also</span></span>

- [<span data-ttu-id="7a415-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7a415-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7a415-120">Метод ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="7a415-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
