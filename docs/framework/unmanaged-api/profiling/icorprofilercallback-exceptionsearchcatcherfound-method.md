---
title: Метод ICorProfilerCallback::ExceptionSearchCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e41378b314b91f42fca9d1039d3011b5eaafe502
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074304"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="4b350-102">Метод ICorProfilerCallback::ExceptionSearchCatcherFound</span><span class="sxs-lookup"><span data-stu-id="4b350-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="4b350-103">Уведомляет профилировщик, что этап поиска обработки исключений был обнаружен обработчик для исключения.</span><span class="sxs-lookup"><span data-stu-id="4b350-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b350-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b350-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b350-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b350-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4b350-106">[in] Идентификатор функции, которая содержит обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="4b350-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b350-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4b350-107">Requirements</span></span>  
 <span data-ttu-id="4b350-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b350-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b350-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b350-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b350-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b350-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b350-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b350-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b350-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4b350-112">See also</span></span>

- [<span data-ttu-id="4b350-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4b350-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
