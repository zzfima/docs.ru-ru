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
ms.openlocfilehash: 4c14b3e8b9d0116d638e2983955598a6c51c405a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790209"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="696b3-102">Метод ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="696b3-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="696b3-103">Уведомляет профилировщик о выгрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="696b3-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="696b3-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="696b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="696b3-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="696b3-106">\[в] определяет сборку, которая выгружается.</span><span class="sxs-lookup"><span data-stu-id="696b3-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="696b3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="696b3-107">Remarks</span></span>  
 <span data-ttu-id="696b3-108">Значение `assemblyId` недопустимо для информационного запроса после возврата метода `AssemblyUnloadStarted` — это последний шанс профилировщика получить сведения об этой сборке.</span><span class="sxs-lookup"><span data-stu-id="696b3-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696b3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="696b3-109">Requirements</span></span>  
 <span data-ttu-id="696b3-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696b3-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="696b3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="696b3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="696b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="696b3-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696b3-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="696b3-114">See also</span></span>

- [<span data-ttu-id="696b3-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="696b3-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="696b3-116">Метод AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="696b3-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
