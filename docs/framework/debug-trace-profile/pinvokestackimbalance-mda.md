---
title: pInvokeStackImbalance MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9da05a84568a6168ed9f450afa48aa6864ed575
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="25eb4-102">pInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="25eb4-102">pInvokeStackImbalance MDA</span></span>
<span data-ttu-id="25eb4-103">Управляемый помощник по отладке (MDA) `pInvokeStackImbalance` активируется, когда среда CLR обнаруживает, что глубина стека после вызова неуправляемого кода не соответствует ожидаемой глубине стека, учитывая соглашение о вызовах, указанное в атрибуте <xref:System.Runtime.InteropServices.DllImportAttribute>, а также объявление параметров в управляемой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="25eb4-103">The `pInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute as well as the declaration of the parameters in the managed signature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25eb4-104">MDA `pInvokeStackImbalance` реализован только для 32-разрядных платформ x86.</span><span class="sxs-lookup"><span data-stu-id="25eb4-104">The `pInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25eb4-105">В .NET Framework версии 3.5 MDA `pInvokeStackImbalance` отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="25eb4-105">In the .NET Framework version 3.5, the `pInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="25eb4-106">При использовании .NET Framework версии 3.5 с Visual Studio 2005 MDA `pInvokeStackImbalance` будет отображаться в списке **Помощники по отладке управляемого кода** диалогового окна **Исключения** (которое отображается при выборе пункта **Исключения** в меню **Отладка**).</span><span class="sxs-lookup"><span data-stu-id="25eb4-106">When you use the .NET Framework version 3.5 with Visual Studio 2005, the `pInvokeStackImbalance` MDA will appear in the **Managed Debugging Assistants** list in the **Exceptions** dialog box (which is displayed when you click **Exceptions** on the **Debug** menu).</span></span> <span data-ttu-id="25eb4-107">Однако установка или снятие флажка **Вызванное** для `pInvokeStackImbalance` не включает и не отключает MDA. Этот флажок управляет только тем, вызывает ли Visual Studio исключение, когда MDA активирован.</span><span class="sxs-lookup"><span data-stu-id="25eb4-107">However, selecting or clearing the **Thrown** check box for `pInvokeStackImbalance` does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="25eb4-108">Симптомы</span><span class="sxs-lookup"><span data-stu-id="25eb4-108">Symptoms</span></span>  
 <span data-ttu-id="25eb4-109">В приложении обнаружено нарушение прав доступа или повреждение памяти при выполнении или отслеживании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="25eb4-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="25eb4-110">Причина</span><span class="sxs-lookup"><span data-stu-id="25eb4-110">Cause</span></span>  
 <span data-ttu-id="25eb4-111">Управляемая сигнатура вызова неуправляемого кода может не соответствовать неуправляемой сигнатуре вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="25eb4-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="25eb4-112">Это несоответствие может быть вызвано тем, что управляемая сигнатура не объявляет правильное количество параметров или не задает соответствующий размер для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="25eb4-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="25eb4-113">MDA также может активироваться, поскольку соглашение о вызовах, возможно указанное атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute>, не соответствует соглашению о вызовах неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="25eb4-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="25eb4-114">Решение</span><span class="sxs-lookup"><span data-stu-id="25eb4-114">Resolution</span></span>  
 <span data-ttu-id="25eb4-115">Просмотрите сигнатуру вызова неуправляемого кода и соглашение о вызовах, чтобы убедиться, что они соответствуют сигнатуре и соглашению о вызовах исходного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="25eb4-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="25eb4-116">Попробуйте явным образом задать соглашение о вызовах для управляемой и неуправляемой сторон.</span><span class="sxs-lookup"><span data-stu-id="25eb4-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="25eb4-117">Также возможно, хотя и маловероятно, что неуправляемая функция внесла дисбаланс в стек по какой-либо другой причине, например из-за ошибки в неуправляемом компиляторе.</span><span class="sxs-lookup"><span data-stu-id="25eb4-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="25eb4-118">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="25eb4-118">Effect on the Runtime</span></span>  
 <span data-ttu-id="25eb4-119">Заставляет все вызовы неуправляемого кода принимать неоптимизированный путь в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="25eb4-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="25eb4-120">Вывод</span><span class="sxs-lookup"><span data-stu-id="25eb4-120">Output</span></span>  
 <span data-ttu-id="25eb4-121">Сообщение MDA предоставляет имя вызова метода вызова неуправляемого кода, который привел к несбалансированности стека вызова.</span><span class="sxs-lookup"><span data-stu-id="25eb4-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span>  <span data-ttu-id="25eb4-122">Пример сообщения вызова неуправляемого кода в методе `SampleMethod`:</span><span class="sxs-lookup"><span data-stu-id="25eb4-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a><span data-ttu-id="25eb4-123">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="25eb4-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="25eb4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="25eb4-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="25eb4-125">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="25eb4-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="25eb4-126">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="25eb4-126">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
