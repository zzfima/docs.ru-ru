---
title: callbackOnCollectedDelegate MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e9f2208f2e309b2433bc158a309284131ae8abd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="c486f-102">callbackOnCollectedDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="c486f-102">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="c486f-103">Управляемый помощник по отладке (MDA) `callbackOnCollectedDelegate` активируется, если делегат маршалируется из управляемого в неуправляемый код как указатель функции, и обратный вызов помещается в данный указатель функции после сбора мусора делегата.</span><span class="sxs-lookup"><span data-stu-id="c486f-103">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c486f-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="c486f-104">Symptoms</span></span>  
 <span data-ttu-id="c486f-105">Нарушение прав доступа происходит при попытке вызова управляемого кода посредством указателей функций, которые были получены из управляемых делегатов.</span><span class="sxs-lookup"><span data-stu-id="c486f-105">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="c486f-106">Такие сбои, не будучи распространенными ошибками среды CLR, могут возникать из-за нарушения прав доступа в коде среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c486f-106">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="c486f-107">Этот сбой не является постоянным; иногда вызов указателя функции выполняется успешно, а иногда происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="c486f-107">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="c486f-108">Этот сбой может возникать только в условиях большой нагрузки или при произвольном числе попыток.</span><span class="sxs-lookup"><span data-stu-id="c486f-108">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c486f-109">Причина</span><span class="sxs-lookup"><span data-stu-id="c486f-109">Cause</span></span>  
 <span data-ttu-id="c486f-110">Делегат, из которого указатель функции был создан и открыт для неуправляемого кода, был собран как мусор.</span><span class="sxs-lookup"><span data-stu-id="c486f-110">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="c486f-111">Когда неуправляемый компонент пытается вызвать указатель функции, он создает нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="c486f-111">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="c486f-112">Этот сбой появляется произвольно, так как он зависит от того, когда выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="c486f-112">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="c486f-113">Если делегат является доступным для коллекции, сборка мусора может произойти после обратного вызова, и тогда вызов выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="c486f-113">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="c486f-114">В других случаях сборка мусора происходит перед обратным вызовом, обратный вызов создает нарушение прав доступа, и программа останавливается.</span><span class="sxs-lookup"><span data-stu-id="c486f-114">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="c486f-115">Вероятность возникновения сбоя зависит от времени между маршалингом делегата и обратным вызовом указателя функции, а также от частоты выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c486f-115">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="c486f-116">Этот сбой бывает разовым при коротком промежутке времени между маршалингом делегата и выполнением обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c486f-116">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="c486f-117">Обычно так происходит, если неуправляемый метод, получающий указатель функции, не сохраняет этот указатель функции для дальнейшего использования, а вместо этого выполняет обратный вызов указателя функции немедленно для завершения работы перед возвратом.</span><span class="sxs-lookup"><span data-stu-id="c486f-117">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="c486f-118">Аналогично сборка мусора происходит чаще, если система работает в условиях большой нагрузки, что увеличивает вероятность того, что сборка мусора произойдет перед выполнением обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c486f-118">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c486f-119">Решение</span><span class="sxs-lookup"><span data-stu-id="c486f-119">Resolution</span></span>  
 <span data-ttu-id="c486f-120">Когда делегат маршалируется как указатель функции, сборщик мусора не может отслеживать его время существования.</span><span class="sxs-lookup"><span data-stu-id="c486f-120">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="c486f-121">Вместо этого код должен хранить ссылку на делегат в течение времени существования неуправляемого указателя функции.</span><span class="sxs-lookup"><span data-stu-id="c486f-121">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="c486f-122">Однако прежде чем делать это, необходимо определить, какой делегат был собран.</span><span class="sxs-lookup"><span data-stu-id="c486f-122">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="c486f-123">При активации MDA он предоставляет имя типа делегата.</span><span class="sxs-lookup"><span data-stu-id="c486f-123">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="c486f-124">Используйте это имя для поиска в коде платформенного вызова или в сигнатурах COM, которые передают этот делегат в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="c486f-124">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="c486f-125">Делегат, вызвавший ошибку, передается вовне посредством одного из этих мест вызова.</span><span class="sxs-lookup"><span data-stu-id="c486f-125">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="c486f-126">Можно также включить в MDA `gcUnmanagedToManaged` принудительный запуск сборки мусора перед каждым обратным вызовом в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="c486f-126">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="c486f-127">Это удалит неопределенность, вносимую сбором мусора, так как обеспечит сбор мусора всегда перед обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="c486f-127">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="c486f-128">Если известно, какой делегат был собран, измените код, чтобы сохранить ссылку на этот делегат на управляемой стороне в течение времени существования маршалированного неуправляемого указателя функции.</span><span class="sxs-lookup"><span data-stu-id="c486f-128">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c486f-129">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="c486f-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="c486f-130">Если делегаты маршалируются как указатели функций, среда выполнения выделяет преобразователя, который осуществляет переход от неуправляемого указателя к управляемому.</span><span class="sxs-lookup"><span data-stu-id="c486f-130">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="c486f-131">Этот преобразователь — то, что неуправляемый код фактически вызывает перед финальным вызовом управляемого делегата.</span><span class="sxs-lookup"><span data-stu-id="c486f-131">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="c486f-132">Без включения MDA `callbackOnCollectedDelegate` неуправляемый код маршалинга удаляется после сбора делегата.</span><span class="sxs-lookup"><span data-stu-id="c486f-132">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="c486f-133">С включением MDA `callbackOnCollectedDelegate` неуправляемый код маршалинга не удаляется немедленно после сбора делегата.</span><span class="sxs-lookup"><span data-stu-id="c486f-133">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="c486f-134">Вместо этого последние 1000 экземпляров хранятся по умолчанию и изменяются, чтобы активировать MDA при вызове.</span><span class="sxs-lookup"><span data-stu-id="c486f-134">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="c486f-135">Преобразователь в конечном счете удаляется после сбора не менее чем 1001 маршалированного делегата.</span><span class="sxs-lookup"><span data-stu-id="c486f-135">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c486f-136">Вывод</span><span class="sxs-lookup"><span data-stu-id="c486f-136">Output</span></span>  
 <span data-ttu-id="c486f-137">MDA сообщает имя типа собранного делегата до попытки обратного вызова в его неуправляемом указателе функции.</span><span class="sxs-lookup"><span data-stu-id="c486f-137">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c486f-138">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="c486f-138">Configuration</span></span>  
 <span data-ttu-id="c486f-139">В следующем примере показаны параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="c486f-139">The following example shows the application configuration options.</span></span> <span data-ttu-id="c486f-140">В нем устанавливается число преобразователей, которые сохраняются MDA, равное 1500.</span><span class="sxs-lookup"><span data-stu-id="c486f-140">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="c486f-141">Значение `listSize` по умолчанию — 1000; минимальное значение — 50; максимальное значение — 2000.</span><span class="sxs-lookup"><span data-stu-id="c486f-141">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="c486f-142">Пример</span><span class="sxs-lookup"><span data-stu-id="c486f-142">Example</span></span>  
 <span data-ttu-id="c486f-143">Следующий пример демонстрирует ситуацию, которая может активировать данный MDA:</span><span class="sxs-lookup"><span data-stu-id="c486f-143">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
```  
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}  
// ---------------------------------------------------  
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {          
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c486f-144">См. также</span><span class="sxs-lookup"><span data-stu-id="c486f-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="c486f-145">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="c486f-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="c486f-146">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c486f-146">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="c486f-147">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="c486f-147">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
