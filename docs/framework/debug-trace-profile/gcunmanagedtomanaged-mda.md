---
title: gcUnmanagedToManaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f662114868832f909d734a482e1dc9aefb841a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150884"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="2987a-102">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="2987a-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="2987a-103">Помощник по отладке управляемого кода (MDA) `gcUnmanagedToManaged` вызывает сбор мусора каждый раз, когда поток переходит из неуправляемого в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="2987a-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2987a-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="2987a-104">Symptoms</span></span>  
 <span data-ttu-id="2987a-105">Приложение, запускающее неуправляемые пользовательские компоненты с помощью модели СОМ и вызова платформы, является причиной недетерминированного нарушения прав доступа в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="2987a-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2987a-106">Причина</span><span class="sxs-lookup"><span data-stu-id="2987a-106">Cause</span></span>  
 <span data-ttu-id="2987a-107">Если приложение выполняет неуправляемые пользовательские компоненты, эти компоненты могут повредить кучу сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2987a-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="2987a-108">Это приводит к нарушению прав доступа в среде CLR при попытке сборщика мусора пройти граф объекта.</span><span class="sxs-lookup"><span data-stu-id="2987a-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2987a-109">Решение</span><span class="sxs-lookup"><span data-stu-id="2987a-109">Resolution</span></span>  
 <span data-ttu-id="2987a-110">Включение этого помощника уменьшает время между тем, когда неуправляемый компонент повреждает кучу сборки мусора, и тем, когда происходит нарушение прав доступа принудительным выполнением сборки мусора перед каждой управляемой передачей.</span><span class="sxs-lookup"><span data-stu-id="2987a-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2987a-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="2987a-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="2987a-112">Вызывает сборку мусора каждый раз, когда поток переходит из неуправляемого в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="2987a-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2987a-113">Вывод</span><span class="sxs-lookup"><span data-stu-id="2987a-113">Output</span></span>  
 <span data-ttu-id="2987a-114">Данный MDA не дает результатов.</span><span class="sxs-lookup"><span data-stu-id="2987a-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="2987a-115">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="2987a-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2987a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2987a-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="2987a-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="2987a-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2987a-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="2987a-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="2987a-119">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2987a-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
