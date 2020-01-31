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
ms.openlocfilehash: 710dbe70b0a2498a3d521cdc813c4ead7ba6442e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866433"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="bcdf8-102">Метод ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="bcdf8-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="bcdf8-103">Уведомляет профилировщик о том, что фаза поиска обработки исключений начала выполнять пользовательский фильтр исключений.</span><span class="sxs-lookup"><span data-stu-id="bcdf8-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcdf8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcdf8-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcdf8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcdf8-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="bcdf8-106">\[в] идентификатор функции, которая содержит фильтр.</span><span class="sxs-lookup"><span data-stu-id="bcdf8-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="bcdf8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bcdf8-107">Requirements</span></span>  
 <span data-ttu-id="bcdf8-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcdf8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcdf8-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcdf8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcdf8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcdf8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcdf8-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcdf8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcdf8-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="bcdf8-112">See also</span></span>

- [<span data-ttu-id="bcdf8-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bcdf8-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bcdf8-114">Метод ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="bcdf8-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
