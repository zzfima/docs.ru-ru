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
ms.openlocfilehash: a96a2a0d6e4bc48a46850aeaadd17c2669419cef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597456"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="c74ff-102">Метод ICorProfilerCallback::AssemblyLoadStarted</span><span class="sxs-lookup"><span data-stu-id="c74ff-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="c74ff-103">Уведомляет профилировщик, что сборка загружается.</span><span class="sxs-lookup"><span data-stu-id="c74ff-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c74ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c74ff-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c74ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c74ff-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c74ff-106">[in] Идентифицирует сборку, которая загружается.</span><span class="sxs-lookup"><span data-stu-id="c74ff-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c74ff-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c74ff-107">Remarks</span></span>  
 <span data-ttu-id="c74ff-108">Значение `assemblyId` не является допустимым для информационного запроса до [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="c74ff-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c74ff-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c74ff-109">Requirements</span></span>  
 <span data-ttu-id="c74ff-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c74ff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c74ff-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c74ff-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c74ff-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c74ff-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c74ff-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c74ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c74ff-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c74ff-114">See also</span></span>

- [<span data-ttu-id="c74ff-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c74ff-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
