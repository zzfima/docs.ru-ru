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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9ee87c926d2377ff8eef53f930fe75251b28ceb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137778"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="bd0e0-102">Метод ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="bd0e0-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="bd0e0-103">Уведомляет профилировщик о выгрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd0e0-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd0e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd0e0-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="bd0e0-106">[in] Идентифицирует сборку, которая вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bd0e0-107">[in] Значение HRESULT, указывающее, была ли сборка выгружается успешно.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd0e0-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd0e0-108">Remarks</span></span>  
 <span data-ttu-id="bd0e0-109">Значение `assemblyId` не является допустимым для информационного запроса после [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) возвращает метод.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="bd0e0-110">Некоторые части выгрузку сборки может по-прежнему после `AssemblyUnloadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="bd0e0-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bd0e0-112">Тем не менее значение HRESULT в `hrStatus` указывает, что в первой части выгрузку сборки выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="bd0e0-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd0e0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="bd0e0-113">Requirements</span></span>  
 <span data-ttu-id="bd0e0-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd0e0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd0e0-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd0e0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd0e0-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd0e0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd0e0-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd0e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0e0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bd0e0-118">See also</span></span>

- [<span data-ttu-id="bd0e0-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bd0e0-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
