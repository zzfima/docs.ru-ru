---
title: ICorProfilerCallback8::DynamicMethodJITCompilationГотовый метод
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175113"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="318fc-102">ICorProfilerCallback8::DynamicMethodJITCompilationГотовый метод</span><span class="sxs-lookup"><span data-stu-id="318fc-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="318fc-103">«Поддерживается в рамках .NET 4.7 и более поздних версиях»</span><span class="sxs-lookup"><span data-stu-id="318fc-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="318fc-104">Уведомляет профайлера всякий раз, когда компиляция динамического метода JIT завершена.</span><span class="sxs-lookup"><span data-stu-id="318fc-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318fc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="318fc-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="318fc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="318fc-106">Parameters</span></span>  
<span data-ttu-id="318fc-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="318fc-107">[in] `functionId`</span></span>  
<span data-ttu-id="318fc-108">Идентификатор функции в памяти, для которой запускается компиляция JIT.</span><span class="sxs-lookup"><span data-stu-id="318fc-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="318fc-109">(в) `hrStatus` Значение, указывавое, была ли компиляция JIT успешным.</span><span class="sxs-lookup"><span data-stu-id="318fc-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="318fc-110">(в) `fIsSafeToBlock` указать, что блокировка может привести к тому, что время выполнения может привести к тому, что поток вызова вернется из этого обратного 
 `true` вызова; `false` указать, что блокировка не повлияет на работу времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="318fc-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="318fc-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="318fc-111">Remarks</span></span>  

<span data-ttu-id="318fc-112">Этот обратный вызов запускается всякий раз, когда компиляция динамического метода JIT закончена.</span><span class="sxs-lookup"><span data-stu-id="318fc-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="318fc-113">Это включает в себя различные заглушки IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="318fc-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="318fc-114">Его цель заключается в предоставлении сценаристам-профилировщикам достаточно информации для идентификации компилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="318fc-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="318fc-115">`functionId`значения не могут быть использованы для разрешения их токенов метаданных, поскольку динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="318fc-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="318fc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="318fc-116">Requirements</span></span>  
 <span data-ttu-id="318fc-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="318fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="318fc-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="318fc-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="318fc-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="318fc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="318fc-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="318fc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318fc-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="318fc-121">See also</span></span>

- [<span data-ttu-id="318fc-122">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="318fc-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="318fc-123">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="318fc-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
