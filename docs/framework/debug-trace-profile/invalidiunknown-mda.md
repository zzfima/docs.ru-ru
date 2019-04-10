---
title: Помощник по отладке управляемого кода invalidIUnknown
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35560b966d5fba60ac35b2eb1e559e196fc868f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223359"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="ecb71-102">Помощник по отладке управляемого кода invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="ecb71-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="ecb71-103">Помощник по отладке управляемого кода (MDA) `invalidIUnknown` активируется, когда недопустимый указатель `IUnknown` передается в управляемый код из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="ecb71-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="ecb71-104">`IUnknown` не удалось возвратить успех при запросе для интерфейса `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="ecb71-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ecb71-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="ecb71-105">Symptoms</span></span>  
 <span data-ttu-id="ecb71-106">Непредвиденная ошибка при маршалинге указателя интерфейса СОМ во время маршалинга аргумента.</span><span class="sxs-lookup"><span data-stu-id="ecb71-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ecb71-107">Причина</span><span class="sxs-lookup"><span data-stu-id="ecb71-107">Cause</span></span>  
 <span data-ttu-id="ecb71-108">Неверная реализация `QueryInterface` в интерфейсе COM, переданном в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="ecb71-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ecb71-109">Решение</span><span class="sxs-lookup"><span data-stu-id="ecb71-109">Resolution</span></span>  
 <span data-ttu-id="ecb71-110">Исправьте реализацию `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="ecb71-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ecb71-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="ecb71-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="ecb71-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="ecb71-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ecb71-113">Вывод</span><span class="sxs-lookup"><span data-stu-id="ecb71-113">Output</span></span>  
 <span data-ttu-id="ecb71-114">Описание ошибки</span><span class="sxs-lookup"><span data-stu-id="ecb71-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ecb71-115">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="ecb71-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecb71-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ecb71-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ecb71-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="ecb71-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ecb71-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ecb71-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
