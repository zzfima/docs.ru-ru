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
ms.openlocfilehash: 08ac7eddf96ac54ce16696355f7d5bb5694f872b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="ca080-102">Метод ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="ca080-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="ca080-103">Уведомляет профилировщик о том, что на поисковом этапе обработки исключений начал выполняться в фильтре исключений, определяемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="ca080-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca080-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca080-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca080-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca080-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ca080-106">[in] Идентификатор функции, которая содержит фильтр.</span><span class="sxs-lookup"><span data-stu-id="ca080-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca080-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ca080-107">Requirements</span></span>  
 <span data-ttu-id="ca080-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca080-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca080-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca080-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca080-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca080-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca080-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca080-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca080-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ca080-112">See Also</span></span>  
 [<span data-ttu-id="ca080-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ca080-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ca080-114">Метод ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="ca080-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
