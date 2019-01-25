---
title: Помощник по отладке управляемого кода raceOnRCWCleanup
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2fe4a5a2886fdbbd36ee491ea66dbce353fb034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717250"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="8edc8-102">Помощник по отладке управляемого кода raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="8edc8-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="8edc8-103">Помощник по отладке управляемого кода (MDA) `raceOnRCWCleanup` активируется, когда среда CLR обнаруживает, что используется [вызываемая оболочка времени выполнения](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW), когда выполняется вызов освобождения с помощью команды, такой как метод <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8edc8-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8edc8-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="8edc8-104">Symptoms</span></span>  
 <span data-ttu-id="8edc8-105">Нарушение прав доступа или повреждение памяти во время или после освобождения RCW с помощью метода <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> или аналогичным способом.</span><span class="sxs-lookup"><span data-stu-id="8edc8-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8edc8-106">Причина</span><span class="sxs-lookup"><span data-stu-id="8edc8-106">Cause</span></span>  
 <span data-ttu-id="8edc8-107">RCW используется в другом потоке или в стеке высвобождения потоков.</span><span class="sxs-lookup"><span data-stu-id="8edc8-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="8edc8-108">RCW, которая используется, не может быть освобождена.</span><span class="sxs-lookup"><span data-stu-id="8edc8-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8edc8-109">Решение</span><span class="sxs-lookup"><span data-stu-id="8edc8-109">Resolution</span></span>  
 <span data-ttu-id="8edc8-110">Не освобождайте RCW, которая может использоваться в текущем или в других потоках.</span><span class="sxs-lookup"><span data-stu-id="8edc8-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8edc8-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="8edc8-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="8edc8-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="8edc8-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8edc8-113">Вывод</span><span class="sxs-lookup"><span data-stu-id="8edc8-113">Output</span></span>  
 <span data-ttu-id="8edc8-114">Сообщение, описывающее ошибку.</span><span class="sxs-lookup"><span data-stu-id="8edc8-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8edc8-115">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="8edc8-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8edc8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8edc8-116">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8edc8-117">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="8edc8-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8edc8-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8edc8-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
