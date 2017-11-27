---
title: invalidFunctionPointerInDelegate MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5e9fd1faacc7be5b95e2bab0d8fdbee105e35498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="267f2-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="267f2-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="267f2-103">Помощник отладки управляемого кода `invalidFunctionPointerInDelegate` (MDA) активируется, когда передается недопустимый указатель функции для создания делегата поверх собственного указателя функции.</span><span class="sxs-lookup"><span data-stu-id="267f2-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="267f2-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="267f2-104">Symptoms</span></span>  
 <span data-ttu-id="267f2-105">Нарушения прав доступа или непредвиденное повреждение памяти при использовании делегата поверх указателя функции.</span><span class="sxs-lookup"><span data-stu-id="267f2-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="267f2-106">Причина</span><span class="sxs-lookup"><span data-stu-id="267f2-106">Cause</span></span>  
 <span data-ttu-id="267f2-107">Был указан недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="267f2-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="267f2-108">Решение</span><span class="sxs-lookup"><span data-stu-id="267f2-108">Resolution</span></span>  
 <span data-ttu-id="267f2-109">Укажите допустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="267f2-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="267f2-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="267f2-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="267f2-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="267f2-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="267f2-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="267f2-112">Output</span></span>  
 <span data-ttu-id="267f2-113">Недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="267f2-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="267f2-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="267f2-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="267f2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="267f2-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="267f2-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="267f2-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="267f2-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="267f2-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
