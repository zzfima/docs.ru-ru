---
title: Метод ICorProfilerCallback::ExceptionSearchFilterEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be91772f07e1a06c7df5b16fd70812e6a522d736
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192593"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="f7bd2-102">Метод ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="f7bd2-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="f7bd2-103">Уведомляет профилировщик о начале этапа поиска обработки исключений выполнение в фильтре исключений, определяемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="f7bd2-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7bd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7bd2-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7bd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7bd2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f7bd2-106">[in] Идентификатор функции, которая содержит фильтр.</span><span class="sxs-lookup"><span data-stu-id="f7bd2-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7bd2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f7bd2-107">Requirements</span></span>  
 <span data-ttu-id="f7bd2-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7bd2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7bd2-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7bd2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7bd2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7bd2-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f7bd2-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f7bd2-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f7bd2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f7bd2-112">See also</span></span>

- [<span data-ttu-id="f7bd2-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f7bd2-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f7bd2-114">Метод ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="f7bd2-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
