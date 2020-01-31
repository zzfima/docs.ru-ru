---
title: Метод ICorProfilerCallback::ModuleLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
ms.openlocfilehash: 88da5a968bf224dc5b6f45ee5d1d2e75386086f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866160"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="35b69-102">Метод ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="35b69-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="35b69-103">Уведомляет профилировщик о загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="35b69-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35b69-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35b69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35b69-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="35b69-106">окне Идентификатор загружаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="35b69-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35b69-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="35b69-107">Remarks</span></span>  
 <span data-ttu-id="35b69-108">Значение `moduleId` недопустимо для информационного запроса, пока не вызван метод [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35b69-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b69-109">Требования</span><span class="sxs-lookup"><span data-stu-id="35b69-109">Requirements</span></span>  
 <span data-ttu-id="35b69-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b69-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b69-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35b69-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35b69-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35b69-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35b69-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b69-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b69-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="35b69-114">See also</span></span>

- [<span data-ttu-id="35b69-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="35b69-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
