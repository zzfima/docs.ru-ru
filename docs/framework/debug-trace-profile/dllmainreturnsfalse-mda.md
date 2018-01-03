---
title: "Помощник по отладке управляемого кода dllMainReturnsFalse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb5de2b1c41d102fbf9fc47db0ff3d8bd72a3bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="4bcd2-102">Помощник по отладке управляемого кода dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="4bcd2-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="4bcd2-103">Помощник по отладке управляемого кода `dllMainReturnsFalse` (MDA) активируется в том случае, если управляемая функция `DllMain` в пользовательской сборке вызывается с причиной DLL_PROCESS_ATTACH и возвращает значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4bcd2-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="4bcd2-104">Symptoms</span></span>  
 <span data-ttu-id="4bcd2-105">Функция `DllMain` возвращает значение FALSE, свидетельствующее о сбое при ее выполнении.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="4bcd2-106">Это может привести к возникновению неопределенных проблем, поскольку функции `DllMain` обычно содержат важный код инициализации.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4bcd2-107">Причина</span><span class="sxs-lookup"><span data-stu-id="4bcd2-107">Cause</span></span>  
 <span data-ttu-id="4bcd2-108">Функция `DllMain` вызывается с причиной DLL_PROCESS_ATTACH для инициализации библиотеки DLL при загрузке.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="4bcd2-109">Если она возвращает значение FALSE, значит инициализация библиотеки DLL завершилась сбоем.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4bcd2-110">Решение</span><span class="sxs-lookup"><span data-stu-id="4bcd2-110">Resolution</span></span>  
 <span data-ttu-id="4bcd2-111">Проанализируйте код функции `DllMain` для указанной библиотеки DLL и определите причину сбоя при инициализации.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4bcd2-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="4bcd2-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="4bcd2-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="4bcd2-114">Он только выводит данные о возвращаемом значении для `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4bcd2-115">Вывод</span><span class="sxs-lookup"><span data-stu-id="4bcd2-115">Output</span></span>  
 <span data-ttu-id="4bcd2-116">Сообщение, указывающее, что функция `DllMain` была вызвана с причиной DLL_PROCESS_ATTACH и вернула значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="4bcd2-117">Обратите внимание, что этот помощник по отладке кода вызывается только в том случае, если в управляемом коде реализована функция `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="4bcd2-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4bcd2-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4bcd2-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bcd2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4bcd2-119">See Also</span></span>  
 [<span data-ttu-id="4bcd2-120">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="4bcd2-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
