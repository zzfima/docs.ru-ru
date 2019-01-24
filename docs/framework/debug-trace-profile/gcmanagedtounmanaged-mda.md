---
title: gcManagedToUnmanaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: add5ba59f8f59fc013f8c04a186b34e711c1490c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537937"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="7f8cb-102">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="7f8cb-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="7f8cb-103">Помощник по отладке управляемого кода (MDA) `gcManagedToUnmanaged` вызывает сбор мусора каждый раз, когда поток переходит из управляемого в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7f8cb-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="7f8cb-104">Symptoms</span></span>  
 <span data-ttu-id="7f8cb-105">Неуправляемый пользовательский компонент вызывает нарушение прав доступа при попытке использования управляемого объекта, предоставленного для COM.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="7f8cb-106">COM-объект выглядит как освобожденный.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-106">The COM object appears to have been released.</span></span> <span data-ttu-id="7f8cb-107">Нарушение прав доступа является недетерминированным.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7f8cb-108">Причина</span><span class="sxs-lookup"><span data-stu-id="7f8cb-108">Cause</span></span>  
 <span data-ttu-id="7f8cb-109">Если неуправляемый компонент не является ссылкой, правильно учитывающей управляемый COM-объект, среда выполнения может собрать управляемый объект, предоставленный в COM, когда неуправляемый компонент еще содержит ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="7f8cb-110">Среда выполнения вызывает метод <xref:System.Runtime.InteropServices.Marshal.Release%2A> во время сборки мусора, поэтому если пользовательский компонент использует этот объект до выполнения сборки мусора, то он еще не будет собираться.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="7f8cb-111">Это источник недетерминированности.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7f8cb-112">Решение</span><span class="sxs-lookup"><span data-stu-id="7f8cb-112">Resolution</span></span>  
 <span data-ttu-id="7f8cb-113">Включение помощника уменьшает время между тем, когда объект станет доступным для коллекции, и вызовом метода <xref:System.Runtime.InteropServices.Marshal.Release%2A>, помогая отследить, какие неуправляемые компоненты сначала пытаются получить доступ к собранному объекту.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7f8cb-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="7f8cb-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="7f8cb-115">Вызывает сборку мусора каждый раз, когда поток переходит из управляемого в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7f8cb-116">Вывод</span><span class="sxs-lookup"><span data-stu-id="7f8cb-116">Output</span></span>  
 <span data-ttu-id="7f8cb-117">Данный MDA не дает результатов.</span><span class="sxs-lookup"><span data-stu-id="7f8cb-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7f8cb-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="7f8cb-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f8cb-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7f8cb-119">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7f8cb-120">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="7f8cb-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7f8cb-121">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="7f8cb-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
- [<span data-ttu-id="7f8cb-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="7f8cb-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
