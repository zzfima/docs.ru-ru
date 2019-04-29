---
title: Метод ICorProfilerCallback::AssemblyUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c95bed520e0a4687541f127c8b39ef7916ef104
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598627"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="627c0-102">Метод ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="627c0-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="627c0-103">Уведомляет профилировщик о выгрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="627c0-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="627c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="627c0-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="627c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="627c0-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="627c0-106">[in] Идентифицирует сборку, которая вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="627c0-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="627c0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="627c0-107">Remarks</span></span>  
 <span data-ttu-id="627c0-108">Значение `assemblyId` не является допустимым для информационного запроса после `AssemblyUnloadStarted` возвращает метод — это последняя возможность профилировщика для получения сведений об этой сборке.</span><span class="sxs-lookup"><span data-stu-id="627c0-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="627c0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="627c0-109">Requirements</span></span>  
 <span data-ttu-id="627c0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="627c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="627c0-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="627c0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="627c0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="627c0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="627c0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="627c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627c0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="627c0-114">See also</span></span>

- [<span data-ttu-id="627c0-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="627c0-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="627c0-116">Метод AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="627c0-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
