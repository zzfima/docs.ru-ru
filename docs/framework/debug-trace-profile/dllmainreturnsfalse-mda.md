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
ms.openlocfilehash: 91d2dfefc8de49770ec5c0b0083767bbb4b76c0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="16f4b-102">Помощник по отладке управляемого кода dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="16f4b-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="16f4b-103">Помощник по отладке управляемого кода `dllMainReturnsFalse` (MDA) активируется в том случае, если управляемая функция `DllMain` в пользовательской сборке вызывается с причиной DLL_PROCESS_ATTACH и возвращает значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="16f4b-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="16f4b-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="16f4b-104">Symptoms</span></span>  
 <span data-ttu-id="16f4b-105">Функция `DllMain` возвращает значение FALSE, свидетельствующее о сбое при ее выполнении.</span><span class="sxs-lookup"><span data-stu-id="16f4b-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="16f4b-106">Это может привести к возникновению неопределенных проблем, поскольку функции `DllMain` обычно содержат важный код инициализации.</span><span class="sxs-lookup"><span data-stu-id="16f4b-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="16f4b-107">Причина</span><span class="sxs-lookup"><span data-stu-id="16f4b-107">Cause</span></span>  
 <span data-ttu-id="16f4b-108">Функция `DllMain` вызывается с причиной DLL_PROCESS_ATTACH для инициализации библиотеки DLL при загрузке.</span><span class="sxs-lookup"><span data-stu-id="16f4b-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="16f4b-109">Если она возвращает значение FALSE, значит инициализация библиотеки DLL завершилась сбоем.</span><span class="sxs-lookup"><span data-stu-id="16f4b-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="16f4b-110">Решение</span><span class="sxs-lookup"><span data-stu-id="16f4b-110">Resolution</span></span>  
 <span data-ttu-id="16f4b-111">Проанализируйте код функции `DllMain` для указанной библиотеки DLL и определите причину сбоя при инициализации.</span><span class="sxs-lookup"><span data-stu-id="16f4b-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="16f4b-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="16f4b-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="16f4b-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="16f4b-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="16f4b-114">Он только выводит данные о возвращаемом значении для `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="16f4b-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="16f4b-115">Вывод</span><span class="sxs-lookup"><span data-stu-id="16f4b-115">Output</span></span>  
 <span data-ttu-id="16f4b-116">Сообщение, указывающее, что функция `DllMain` была вызвана с причиной DLL_PROCESS_ATTACH и вернула значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="16f4b-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="16f4b-117">Обратите внимание, что этот помощник по отладке кода вызывается только в том случае, если в управляемом коде реализована функция `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="16f4b-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="16f4b-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="16f4b-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="16f4b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="16f4b-119">See Also</span></span>  
 [<span data-ttu-id="16f4b-120">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="16f4b-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
