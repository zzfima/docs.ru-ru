---
title: Метод ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: f0000e9b063022e828e52b9b940ec6f4e0ce4165
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445907"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="0b1f1-102">Метод ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="0b1f1-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="0b1f1-103">Уведомляет профилировщик о выгрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b1f1-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="0b1f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b1f1-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0b1f1-106">окне Идентификатор выгружается модуля.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b1f1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b1f1-107">Remarks</span></span>  
 <span data-ttu-id="0b1f1-108">Значение `moduleId` недопустимо для информационного запроса после возврата метода `ModuleUnloadStarted` — это последний шанс профилировщика получить сведения об этом модуле.</span><span class="sxs-lookup"><span data-stu-id="0b1f1-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b1f1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0b1f1-109">Requirements</span></span>  
 <span data-ttu-id="0b1f1-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b1f1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b1f1-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b1f1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b1f1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b1f1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b1f1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b1f1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1f1-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b1f1-114">See also</span></span>

- [<span data-ttu-id="0b1f1-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0b1f1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0b1f1-116">Метод ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="0b1f1-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
