---
title: Метод ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 01404d23707be90b6b15cf741632400d49f164de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445148"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="84b88-102">Метод ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="84b88-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="84b88-103">Уведомляет профилировщик о том, что сборка была выгружена.</span><span class="sxs-lookup"><span data-stu-id="84b88-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84b88-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84b88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84b88-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="84b88-106">окне Определяет выгрузку сборки.</span><span class="sxs-lookup"><span data-stu-id="84b88-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="84b88-107">окне Значение HRESULT, указывающее, успешно ли выгружена сборка.</span><span class="sxs-lookup"><span data-stu-id="84b88-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84b88-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="84b88-108">Remarks</span></span>  
 <span data-ttu-id="84b88-109">Значение `assemblyId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: ассемблюнлоадстартед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="84b88-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="84b88-110">Некоторые части выгрузки сборки могут продолжаться после обратного вызова `AssemblyUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="84b88-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="84b88-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="84b88-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="84b88-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть выгрузки сборки завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="84b88-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84b88-113">Требования</span><span class="sxs-lookup"><span data-stu-id="84b88-113">Requirements</span></span>  
 <span data-ttu-id="84b88-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84b88-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84b88-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84b88-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84b88-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84b88-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84b88-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84b88-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b88-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="84b88-118">See also</span></span>

- [<span data-ttu-id="84b88-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="84b88-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
