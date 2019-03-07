---
title: Метод ICorProfilerCallback::AssemblyLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbb9a48fc4795f2e5f074369318fec6d4152d9d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468758"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="9ea71-102">Метод ICorProfilerCallback::AssemblyLoadStarted</span><span class="sxs-lookup"><span data-stu-id="9ea71-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="9ea71-103">Уведомляет профилировщик, что сборка загружается.</span><span class="sxs-lookup"><span data-stu-id="9ea71-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ea71-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ea71-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ea71-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="9ea71-106">[in] Идентифицирует сборку, которая загружается.</span><span class="sxs-lookup"><span data-stu-id="9ea71-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ea71-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ea71-107">Remarks</span></span>  
 <span data-ttu-id="9ea71-108">Значение `assemblyId` не является допустимым для информационного запроса до [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="9ea71-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea71-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9ea71-109">Requirements</span></span>  
 <span data-ttu-id="9ea71-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ea71-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea71-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ea71-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ea71-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ea71-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ea71-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea71-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea71-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9ea71-114">See also</span></span>
- [<span data-ttu-id="9ea71-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9ea71-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
