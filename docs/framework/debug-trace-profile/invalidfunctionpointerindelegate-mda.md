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
ms.openlocfilehash: 723f51e14c314bde40c34d629ba7fc4f6276c633
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217377"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="c477d-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="c477d-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="c477d-103">Помощник отладки управляемого кода `invalidFunctionPointerInDelegate` (MDA) активируется, когда передается недопустимый указатель функции для создания делегата поверх собственного указателя функции.</span><span class="sxs-lookup"><span data-stu-id="c477d-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c477d-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="c477d-104">Symptoms</span></span>  
 <span data-ttu-id="c477d-105">Нарушения прав доступа или непредвиденное повреждение памяти при использовании делегата поверх указателя функции.</span><span class="sxs-lookup"><span data-stu-id="c477d-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c477d-106">Причина</span><span class="sxs-lookup"><span data-stu-id="c477d-106">Cause</span></span>  
 <span data-ttu-id="c477d-107">Был указан недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="c477d-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c477d-108">Решение</span><span class="sxs-lookup"><span data-stu-id="c477d-108">Resolution</span></span>  
 <span data-ttu-id="c477d-109">Укажите допустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="c477d-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c477d-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="c477d-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="c477d-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="c477d-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c477d-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="c477d-112">Output</span></span>  
 <span data-ttu-id="c477d-113">Недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="c477d-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c477d-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="c477d-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c477d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="c477d-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c477d-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="c477d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c477d-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c477d-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
