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
ms.openlocfilehash: 40cb666c47c690dc930ec2cb7f6c89662464780e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445912"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="74471-102">Метод ICorProfilerCallback::ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="74471-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="74471-103">Уведомляет профилировщик о завершении выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="74471-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74471-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74471-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74471-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74471-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="74471-106">окне Идентификатор выгруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="74471-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="74471-107">окне Значение HRESULT, указывающее, успешно ли выгружен модуль.</span><span class="sxs-lookup"><span data-stu-id="74471-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74471-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="74471-108">Remarks</span></span>  
 <span data-ttu-id="74471-109">Значение `moduleId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="74471-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="74471-110">Некоторые части выгрузки класса могут продолжаться после обратного вызова `ModuleUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="74471-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="74471-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="74471-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="74471-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть выгрузки модуля успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="74471-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74471-113">Требования</span><span class="sxs-lookup"><span data-stu-id="74471-113">Requirements</span></span>  
 <span data-ttu-id="74471-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74471-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74471-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74471-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74471-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74471-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74471-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74471-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74471-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="74471-118">See also</span></span>

- [<span data-ttu-id="74471-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="74471-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
