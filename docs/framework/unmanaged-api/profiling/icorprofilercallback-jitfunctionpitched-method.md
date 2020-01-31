---
title: Метод ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: cda629b7a6560ca5d731cd88cffc2cffd3486d8a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866225"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="ddab7-102">Метод ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="ddab7-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="ddab7-103">Оповещает профилировщик о том, что JIT-скомпилированная функция была удалена из памяти.</span><span class="sxs-lookup"><span data-stu-id="ddab7-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddab7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddab7-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddab7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddab7-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ddab7-106">окне Идентификатор удаленной функции.</span><span class="sxs-lookup"><span data-stu-id="ddab7-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddab7-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="ddab7-107">Remarks</span></span>  
 <span data-ttu-id="ddab7-108">Если вызывается Удаленная функция, профилировщик получит новые события JIT-компиляции при повторной компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="ddab7-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="ddab7-109">В настоящее время JIT-компилятор среды CLR не удаляет функции из памяти, поэтому этот обратный вызов сейчас не используется и не будет получен профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="ddab7-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="ddab7-110">Значение `functionId` недопустимо, пока функция не будет перекомпилирована.</span><span class="sxs-lookup"><span data-stu-id="ddab7-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="ddab7-111">При повторной компиляции функции будет использоваться то же значение `functionId`.</span><span class="sxs-lookup"><span data-stu-id="ddab7-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddab7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ddab7-112">Requirements</span></span>  
 <span data-ttu-id="ddab7-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddab7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddab7-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ddab7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ddab7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddab7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddab7-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddab7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddab7-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddab7-117">See also</span></span>

- [<span data-ttu-id="ddab7-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ddab7-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
