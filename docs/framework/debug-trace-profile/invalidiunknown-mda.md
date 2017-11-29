---
title: "Помощник по отладке управляемого кода invalidIUnknown"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04fdc96168823397296449ebc25ccdded1ea55c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="2e6f9-102">Помощник по отладке управляемого кода invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="2e6f9-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="2e6f9-103">Помощник по отладке управляемого кода (MDA) `invalidIUnknown` активируется, когда недопустимый указатель `IUnknown` передается в управляемый код из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="2e6f9-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="2e6f9-104">`IUnknown` не удалось возвратить успех при запросе для интерфейса `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="2e6f9-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2e6f9-105">Признаки</span><span class="sxs-lookup"><span data-stu-id="2e6f9-105">Symptoms</span></span>  
 <span data-ttu-id="2e6f9-106">Непредвиденная ошибка при маршалинге указателя интерфейса СОМ во время маршалинга аргумента.</span><span class="sxs-lookup"><span data-stu-id="2e6f9-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2e6f9-107">Причина</span><span class="sxs-lookup"><span data-stu-id="2e6f9-107">Cause</span></span>  
 <span data-ttu-id="2e6f9-108">Неверная реализация `QueryInterface` в интерфейсе COM, переданном в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="2e6f9-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2e6f9-109">Решение</span><span class="sxs-lookup"><span data-stu-id="2e6f9-109">Resolution</span></span>  
 <span data-ttu-id="2e6f9-110">Исправьте реализацию `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="2e6f9-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2e6f9-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="2e6f9-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="2e6f9-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="2e6f9-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2e6f9-113">Вывод</span><span class="sxs-lookup"><span data-stu-id="2e6f9-113">Output</span></span>  
 <span data-ttu-id="2e6f9-114">Описание ошибки</span><span class="sxs-lookup"><span data-stu-id="2e6f9-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="2e6f9-115">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="2e6f9-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e6f9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2e6f9-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="2e6f9-117">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="2e6f9-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="2e6f9-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2e6f9-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
