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
ms.openlocfilehash: d39dbf44b21400c8eb5a7abf361dc868b8d39a22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756094"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="7022e-102">Метод ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="7022e-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="7022e-103">Уведомляет профилировщик о начале этапа поиска обработки исключений выполнение в фильтре исключений, определяемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="7022e-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7022e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7022e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7022e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7022e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7022e-106">[in] Идентификатор функции, которая содержит фильтр.</span><span class="sxs-lookup"><span data-stu-id="7022e-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7022e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7022e-107">Requirements</span></span>  
 <span data-ttu-id="7022e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7022e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7022e-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7022e-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7022e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7022e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7022e-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7022e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7022e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7022e-112">See also</span></span>

- [<span data-ttu-id="7022e-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7022e-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7022e-114">Метод ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="7022e-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
