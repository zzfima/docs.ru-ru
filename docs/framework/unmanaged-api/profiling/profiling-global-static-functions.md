---
title: Глобальные статические функции профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860870"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="b1500-102">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="b1500-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="b1500-103">В этом разделе описываются неуправляемые функции API, используемые API профилирования.</span><span class="sxs-lookup"><span data-stu-id="b1500-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1500-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b1500-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="b1500-105">.NET Framework функции профилирования версии 1</span><span class="sxs-lookup"><span data-stu-id="b1500-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="b1500-106">Функция FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="b1500-106">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="b1500-107">Уведомляет профилировщик о передаче управления в функцию.</span><span class="sxs-lookup"><span data-stu-id="b1500-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="b1500-108">Не рекомендуется использовать в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="b1500-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="b1500-109">Функция FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="b1500-109">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="b1500-110">Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="b1500-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="b1500-111">Не рекомендуется использовать в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="b1500-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="b1500-112">Функция FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="b1500-112">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="b1500-113">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="b1500-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="b1500-114">Не рекомендуется использовать в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="b1500-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="b1500-115">Функции профилирования .NET Framework версии 2</span><span class="sxs-lookup"><span data-stu-id="b1500-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="b1500-116">Функция FunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b1500-116">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="b1500-117">Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в обратных вызовах [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)и [FunctionTailcall2](functiontailcall2-function.md) для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="b1500-118">Также позволяет профилировщику указать, требуется ли получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="b1500-119">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="b1500-119">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="b1500-120">Уведомляет профилировщик о передаче управления в функцию и предоставляет сведения о кадре стека и аргументах функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="b1500-121">Не рекомендуется использовать в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b1500-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="b1500-122">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="b1500-122">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="b1500-123">Уведомляет профилировщик о том, что функция собирается вернуться к вызывающему объекту, и предоставляет сведения о кадре стека и возвращаемом значении функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="b1500-124">Не рекомендуется использовать в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b1500-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="b1500-125">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="b1500-125">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="b1500-126">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail и предоставляет сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="b1500-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="b1500-127">Не рекомендуется использовать в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b1500-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="b1500-128">Функция StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="b1500-128">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="b1500-129">Предоставляет профилировщику сведения о каждом управляемом кадре и каждом запуске неуправляемых кадров в стеке во время прохода стека, который инициируется методом [ICorProfilerInfo2::D остаккснапшот](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b1500-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="b1500-130">Функции профилирования .NET Framework версии 4</span><span class="sxs-lookup"><span data-stu-id="b1500-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="b1500-131">Функция FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="b1500-131">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="b1500-132">Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в ответных вызовах [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)или[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="b1500-133">Также позволяет профилировщику указывать, хотят ли они получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="b1500-134">`FunctionIDMapper2` расширяет функцию [FunctionIDMapper](functionidmapper-function.md) с помощью параметра `clientData`, который профилировщики могут использовать для устранения неоднозначности между средами выполнения.</span><span class="sxs-lookup"><span data-stu-id="b1500-134">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="b1500-135">Функция FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b1500-135">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="b1500-136">Уведомляет профилировщик о передаче управления в функцию.</span><span class="sxs-lookup"><span data-stu-id="b1500-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="b1500-137">Функция FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b1500-137">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="b1500-138">Уведомляет профилировщик о передаче управления в функцию и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) для получения кадра стека и аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="b1500-139">Функция FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b1500-139">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="b1500-140">Уведомляет профилировщик о том, что управление возвращается из функции.</span><span class="sxs-lookup"><span data-stu-id="b1500-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="b1500-141">Функция FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b1500-141">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="b1500-142">Уведомляет профилировщик о том, что управление возвращается из функции, и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) для получения кадра стека и возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="b1500-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="b1500-143">Функция FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b1500-143">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="b1500-144">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="b1500-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="b1500-145">Функция FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b1500-145">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="b1500-146">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail, и предоставляет маркер, который можно передать в [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) для получения кадра стека.</span><span class="sxs-lookup"><span data-stu-id="b1500-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b1500-147">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b1500-147">Related Sections</span></span>  
 [<span data-ttu-id="b1500-148">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="b1500-148">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="b1500-149">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b1500-149">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="b1500-150">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="b1500-150">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="b1500-151">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="b1500-151">Profiling Structures</span></span>](profiling-structures.md)
