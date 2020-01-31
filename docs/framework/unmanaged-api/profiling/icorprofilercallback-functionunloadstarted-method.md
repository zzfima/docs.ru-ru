---
title: Метод ICorProfilerCallback::FunctionUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: 2b228337a55d50b94da966b45877e2000b3c03e4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866330"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="36d5b-102">Метод ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="36d5b-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="36d5b-103">Уведомляет профилировщик о запуске среды выполнения для выгрузки функции.</span><span class="sxs-lookup"><span data-stu-id="36d5b-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36d5b-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="36d5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36d5b-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="36d5b-106">\[в] идентификатор выгрузки функции.</span><span class="sxs-lookup"><span data-stu-id="36d5b-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="36d5b-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="36d5b-107">Remarks</span></span>  
 <span data-ttu-id="36d5b-108">Значение параметра `functionId` больше не является допустимым после возврата этим методом вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="36d5b-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d5b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="36d5b-109">Requirements</span></span>  
 <span data-ttu-id="36d5b-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36d5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d5b-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36d5b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36d5b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36d5b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36d5b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d5b-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="36d5b-114">See also</span></span>

- [<span data-ttu-id="36d5b-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="36d5b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
