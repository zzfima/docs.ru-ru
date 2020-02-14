---
title: illegalPrepareConstrainedRegion MDA
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: b80d6160876834b22e8d9d1eb7112b8b67c15fcc
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216465"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="22b09-102">illegalPrepareConstrainedRegion MDA</span><span class="sxs-lookup"><span data-stu-id="22b09-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="22b09-103">Помощник по отладке управляемого кода (MDA) `illegalPrepareConstrainedRegion` запускается, если сразу же после вызова метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> не следует инструкция `try` обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="22b09-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="22b09-104">Это ограничение используется на уровне MSIL, поэтому между вызовом и `try` можно размещать текст, не приводящий к созданию кода, например комментарии.</span><span class="sxs-lookup"><span data-stu-id="22b09-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="22b09-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="22b09-105">Symptoms</span></span>  
 <span data-ttu-id="22b09-106">Область ограниченного выполнения, которая никогда не рассматривается в виде такой области, но представляет собой простой блок обработки исключений (`finally` или `catch`).</span><span class="sxs-lookup"><span data-stu-id="22b09-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="22b09-107">Поэтому эта область не запускается в случае нехватки памяти или прерывания потока.</span><span class="sxs-lookup"><span data-stu-id="22b09-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="22b09-108">Причина</span><span class="sxs-lookup"><span data-stu-id="22b09-108">Cause</span></span>  
 <span data-ttu-id="22b09-109">Вы не следуете шаблону подготовки для области ограниченного выполнения.</span><span class="sxs-lookup"><span data-stu-id="22b09-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="22b09-110">Это ошибка.</span><span class="sxs-lookup"><span data-stu-id="22b09-110">This is an error event.</span></span> <span data-ttu-id="22b09-111">Вызов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, используемый для пометки обработчиков исключений как представление CER в их `catch`/`finally`/`fault`/блоки должны использоваться непосредственно перед инструкцией `filter`.`try`</span><span class="sxs-lookup"><span data-stu-id="22b09-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="22b09-112">Решение</span><span class="sxs-lookup"><span data-stu-id="22b09-112">Resolution</span></span>  
 <span data-ttu-id="22b09-113">Убедитесь, что вызов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> выполняется непосредственно перед инструкцией `try`.</span><span class="sxs-lookup"><span data-stu-id="22b09-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="22b09-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="22b09-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="22b09-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="22b09-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="22b09-116">Вывод</span><span class="sxs-lookup"><span data-stu-id="22b09-116">Output</span></span>  
 <span data-ttu-id="22b09-117">Помощник по отладке управляемого кода отображает имя метода, вызывающего метод <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, смещение MSIL и сообщение о том, что вызов метода выполняется не перед началом блока try.</span><span class="sxs-lookup"><span data-stu-id="22b09-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="22b09-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="22b09-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="22b09-119">Пример</span><span class="sxs-lookup"><span data-stu-id="22b09-119">Example</span></span>  
 <span data-ttu-id="22b09-120">В следующем примере кода показан шаблон, который запускает этот помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="22b09-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="22b09-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="22b09-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="22b09-122">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="22b09-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="22b09-123">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="22b09-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
