---
title: Помощник по отладке управляемого кода pInvokeLog
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7fe0b33bbd77143da6d2f4a26b170e4d7afe1fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104472"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="1280e-102">Помощник по отладке управляемого кода pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="1280e-102">pInvokeLog MDA</span></span>
<span data-ttu-id="1280e-103">Помощник по отладке управляемого кода `pInvokeLog` активируется для каждой уникальной сигнатуры вызова неуправляемого кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1280e-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1280e-104">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="1280e-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="1280e-105">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="1280e-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1280e-106">Вывод</span><span class="sxs-lookup"><span data-stu-id="1280e-106">Output</span></span>  
 <span data-ttu-id="1280e-107">Сообщение, указывающее на сигнатуру вызова неуправляемого кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1280e-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="1280e-108">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="1280e-108">Configuration</span></span>  
 <span data-ttu-id="1280e-109">Каждый совпадающий элемент фильтрует DLL-файлы, к которым выполняются вызовы неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="1280e-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1280e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1280e-110">See also</span></span>

- [<span data-ttu-id="1280e-111">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="1280e-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="1280e-112">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="1280e-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
