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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212522"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="ba846-102">Интерфейс ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="ba846-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="ba846-103">Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.</span><span class="sxs-lookup"><span data-stu-id="ba846-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba846-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ba846-104">Methods</span></span>  
  
|<span data-ttu-id="ba846-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ba846-105">Method</span></span>|<span data-ttu-id="ba846-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ba846-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba846-107">Метод Deactivate</span><span class="sxs-lookup"><span data-stu-id="ba846-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="ba846-108">В результате `ICorDebugStepper` для отмены последней команды шага, оно получено.</span><span class="sxs-lookup"><span data-stu-id="ba846-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="ba846-109">Метод IsActive</span><span class="sxs-lookup"><span data-stu-id="ba846-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="ba846-110">Получает значение, указывающее, является ли это `ICorDebugStepper` в данный момент выполняет этап.</span><span class="sxs-lookup"><span data-stu-id="ba846-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="ba846-111">Метод SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="ba846-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="ba846-112">Задает CorDebugIntercept значение, указывающее типы кода, который осуществляется пошаговое.</span><span class="sxs-lookup"><span data-stu-id="ba846-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="ba846-113">Метод SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="ba846-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="ba846-114">Задает значение, указывающее, является ли вызовы [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) значения аргументов, машинному коду или код на промежуточном языке (MSIL) метода, который является в настоящее время шаг.</span><span class="sxs-lookup"><span data-stu-id="ba846-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="ba846-115">Метод SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="ba846-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="ba846-116">Задает CorDebugUnmappedStop значение, указывающее тип кода, в котором выполнение будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="ba846-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="ba846-117">Метод Step</span><span class="sxs-lookup"><span data-stu-id="ba846-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="ba846-118">В результате `ICorDebugStepper` на один шаг через содержащую и при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.</span><span class="sxs-lookup"><span data-stu-id="ba846-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="ba846-119">Метод StepOut</span><span class="sxs-lookup"><span data-stu-id="ba846-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="ba846-120">В результате `ICorDebugStepper` один шаг через содержащую и завершенной, если текущий кадр возвращает управление в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="ba846-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="ba846-121">Метод StepRange</span><span class="sxs-lookup"><span data-stu-id="ba846-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="ba846-122">В результате `ICorDebugStepper` на один шаг через содержащую и возвратить при достижении кода за последним из указанных диапазонов.</span><span class="sxs-lookup"><span data-stu-id="ba846-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba846-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba846-123">Remarks</span></span>  
 <span data-ttu-id="ba846-124">`ICorDebugStepper` Интерфейс выполняет следующие функции:</span><span class="sxs-lookup"><span data-stu-id="ba846-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="ba846-125">Он выступает в качестве идентификатора между командой шага, выданный и выполнении этой команды.</span><span class="sxs-lookup"><span data-stu-id="ba846-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="ba846-126">Он обеспечивает центральный интерфейс для инкапсуляции всех пошагового выполнения, которое может быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="ba846-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="ba846-127">Она позволяет преждевременно отменить были выполнены вышеуказанные операции.</span><span class="sxs-lookup"><span data-stu-id="ba846-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="ba846-128">Может существовать несколько шагов на поток.</span><span class="sxs-lookup"><span data-stu-id="ba846-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="ba846-129">Например могут быть точки останова при шаг с обходом функции и пользователь может потребоваться начать новую операцию пошагового выполнения внутри этой функции.</span><span class="sxs-lookup"><span data-stu-id="ba846-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="ba846-130">Это отладчик для определения способа обработки такой ситуации.</span><span class="sxs-lookup"><span data-stu-id="ba846-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="ba846-131">Отладчик может потребоваться отменить пошагового выполнения исходной операции или вложить две операции.</span><span class="sxs-lookup"><span data-stu-id="ba846-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="ba846-132">`ICorDebugStepper` Интерфейс поддерживает две возможности.</span><span class="sxs-lookup"><span data-stu-id="ba846-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="ba846-133">Шаг может мигрировать между потоками, если среда CLR (CLR) делает вызов нескольких потоков, маршалируется.</span><span class="sxs-lookup"><span data-stu-id="ba846-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba846-134">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ba846-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba846-135">Требования</span><span class="sxs-lookup"><span data-stu-id="ba846-135">Requirements</span></span>  
 <span data-ttu-id="ba846-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba846-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba846-137">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba846-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba846-138">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba846-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba846-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba846-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba846-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ba846-140">See also</span></span>

- [<span data-ttu-id="ba846-141">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ba846-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
