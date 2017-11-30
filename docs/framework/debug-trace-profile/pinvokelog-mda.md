---
title: "Помощник по отладке управляемого кода pInvokeLog"
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
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4842d838fd5b4fee29187f118c784c55e0eb13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="42efc-102">Помощник по отладке управляемого кода pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="42efc-102">pInvokeLog MDA</span></span>
<span data-ttu-id="42efc-103">Помощник по отладке управляемого кода `pInvokeLog` активируется для каждой уникальной сигнатуры вызова неуправляемого кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="42efc-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="42efc-104">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="42efc-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="42efc-105">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="42efc-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="42efc-106">Вывод</span><span class="sxs-lookup"><span data-stu-id="42efc-106">Output</span></span>  
 <span data-ttu-id="42efc-107">Сообщение, указывающее на сигнатуру вызова неуправляемого кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="42efc-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="42efc-108">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="42efc-108">Configuration</span></span>  
 <span data-ttu-id="42efc-109">Каждый совпадающий элемент фильтрует DLL-файлы, к которым выполняются вызовы неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="42efc-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42efc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="42efc-110">See Also</span></span>  
 [<span data-ttu-id="42efc-111">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="42efc-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="42efc-112">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="42efc-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
