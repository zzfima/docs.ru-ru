---
title: invalidFunctionPointerInDelegate MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff026ddd9f9dc7c1556c55b285958dad7139e8eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699315"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="14c9b-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="14c9b-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="14c9b-103">Помощник отладки управляемого кода `invalidFunctionPointerInDelegate` (MDA) активируется, когда передается недопустимый указатель функции для создания делегата поверх собственного указателя функции.</span><span class="sxs-lookup"><span data-stu-id="14c9b-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="14c9b-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="14c9b-104">Symptoms</span></span>  
 <span data-ttu-id="14c9b-105">Нарушения прав доступа или непредвиденное повреждение памяти при использовании делегата поверх указателя функции.</span><span class="sxs-lookup"><span data-stu-id="14c9b-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="14c9b-106">Причина</span><span class="sxs-lookup"><span data-stu-id="14c9b-106">Cause</span></span>  
 <span data-ttu-id="14c9b-107">Был указан недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="14c9b-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="14c9b-108">Решение</span><span class="sxs-lookup"><span data-stu-id="14c9b-108">Resolution</span></span>  
 <span data-ttu-id="14c9b-109">Укажите допустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="14c9b-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="14c9b-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="14c9b-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="14c9b-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="14c9b-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="14c9b-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="14c9b-112">Output</span></span>  
 <span data-ttu-id="14c9b-113">Недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="14c9b-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="14c9b-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="14c9b-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14c9b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="14c9b-115">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="14c9b-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="14c9b-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="14c9b-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="14c9b-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
