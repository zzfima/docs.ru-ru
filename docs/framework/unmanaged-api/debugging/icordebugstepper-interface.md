---
title: Интерфейс ICorDebugStepper
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
ms.openlocfilehash: 3ca062231fd482c1f0d888935e882513461838ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137594"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="72aea-102">Интерфейс ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="72aea-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="72aea-103">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="72aea-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72aea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="72aea-104">Methods</span></span>  
  
|<span data-ttu-id="72aea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="72aea-105">Method</span></span>|<span data-ttu-id="72aea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="72aea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72aea-107">Метод Deactivate</span><span class="sxs-lookup"><span data-stu-id="72aea-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="72aea-108">Приводит к тому, что эта `ICorDebugStepper` отменяет полученную команду последнего шага.</span><span class="sxs-lookup"><span data-stu-id="72aea-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="72aea-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="72aea-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="72aea-110">Возвращает значение, указывающее, выполняется ли в данный момент шаг в данный `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="72aea-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="72aea-111">Метод SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="72aea-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="72aea-112">Задает значение CorDebugIntercept, указывающее типы кода, в который выполняется пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="72aea-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="72aea-113">Метод SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="72aea-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="72aea-114">Задает значение, указывающее, должны ли вызовы метода [ICorDebugStepper:: степранже](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) передавать значения аргументов, относящихся к машинному коду или коду кода на языке MSIL, который проходит через шаг.</span><span class="sxs-lookup"><span data-stu-id="72aea-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="72aea-115">Метод SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="72aea-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="72aea-116">Задает значение Кордебугунмаппедстоп, указывающее тип несопоставленного кода, в котором выполнение будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="72aea-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="72aea-117">Метод Step</span><span class="sxs-lookup"><span data-stu-id="72aea-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="72aea-118">Приводит к тому, что этот `ICorDebugStepper` пошаговым выполнением содержащего его потока и, при необходимости, для продолжения пошагового выполнения функций, которые вызываются в потоке.</span><span class="sxs-lookup"><span data-stu-id="72aea-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="72aea-119">Метод StepOut</span><span class="sxs-lookup"><span data-stu-id="72aea-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="72aea-120">Приводит к тому, что этот `ICorDebugStepper` пошаговым путем через содержащий его поток и завершается, когда текущий кадр возвращает управление вызывающему кадру.</span><span class="sxs-lookup"><span data-stu-id="72aea-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="72aea-121">Метод StepRange</span><span class="sxs-lookup"><span data-stu-id="72aea-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="72aea-122">Приводит к тому, что этот `ICorDebugStepper` пошаговым выполнением содержащего его потока и возвращаться при достижении кода, находящегося за последним из указанных диапазонов.</span><span class="sxs-lookup"><span data-stu-id="72aea-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72aea-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="72aea-123">Remarks</span></span>  
 <span data-ttu-id="72aea-124">Интерфейс `ICorDebugStepper` выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="72aea-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="72aea-125">Он выступает в качестве идентификатора между выдаваемыми командой Step и завершением этой команды.</span><span class="sxs-lookup"><span data-stu-id="72aea-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="72aea-126">Он предоставляет центральный интерфейс для инкапсуляции всех шагов, которые можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="72aea-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="72aea-127">Он позволяет преждевременно отменить операцию пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="72aea-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="72aea-128">Для каждого потока может существовать несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="72aea-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="72aea-129">Например, при пошаговом выполнении функции может быть достигнута точка останова, и пользователю может потребоваться начать новую операцию пошагового выполнения внутри этой функции.</span><span class="sxs-lookup"><span data-stu-id="72aea-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="72aea-130">Для определения способа решения этой проблемы отладчику необходимо присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="72aea-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="72aea-131">Отладчик может захотеть отменить исходную операцию пошагового выполнения или вложить две операции.</span><span class="sxs-lookup"><span data-stu-id="72aea-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="72aea-132">Интерфейс `ICorDebugStepper` поддерживает оба варианта.</span><span class="sxs-lookup"><span data-stu-id="72aea-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="72aea-133">Средство организации пошагового выполнения может переноситься между потоками, если среда CLR выполняет перекрестный потоковый вызов.</span><span class="sxs-lookup"><span data-stu-id="72aea-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72aea-134">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="72aea-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72aea-135">Требования</span><span class="sxs-lookup"><span data-stu-id="72aea-135">Requirements</span></span>  
 <span data-ttu-id="72aea-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72aea-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72aea-137">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72aea-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72aea-138">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72aea-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72aea-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72aea-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72aea-140">См. также</span><span class="sxs-lookup"><span data-stu-id="72aea-140">See also</span></span>

- [<span data-ttu-id="72aea-141">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="72aea-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
