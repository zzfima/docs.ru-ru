---
title: virtualCERCall MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2c8712837dab17f70be32617711c1bad9349508
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086082"
---
# <a name="virtualcercall-mda"></a><span data-ttu-id="853ba-102">virtualCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="853ba-102">virtualCERCall MDA</span></span>
<span data-ttu-id="853ba-103">Помощник по отладке управляемого кода (MDA) `virtualCERCall` активируется как предупреждение, указывающее на то, что точка вызова в графе вызовов для области ограниченного выполнения (CER) относится к виртуальному целевому объекту, то есть к виртуальному вызову неконечного виртуального метода или к вызову с помощью интерфейса.</span><span class="sxs-lookup"><span data-stu-id="853ba-103">The `virtualCERCall` managed debugging assistant (MDA) is activated as a warning indicating that a call site within a constrained execution region (CER) call graph refers to a virtual target, that is, a virtual call to a non-final virtual method or a call using an interface.</span></span> <span data-ttu-id="853ba-104">Среда CLR не может спрогнозировать конечный метод этих вызовов только на основании промежуточного языка и анализа метаданных.</span><span class="sxs-lookup"><span data-stu-id="853ba-104">The common language runtime (CLR) cannot predict the destination method of these calls from the intermediate language and metadata analysis alone.</span></span> <span data-ttu-id="853ba-105">В результате дерево вызовов невозможно подготовить как часть графа CER и прерывания потока в этом поддереве невозможно блокировать автоматически.</span><span class="sxs-lookup"><span data-stu-id="853ba-105">As a result, the call tree cannot be prepared as part of the CER graph and thread aborts in that subtree cannot be automatically blocked.</span></span> <span data-ttu-id="853ba-106">Этот помощник по отладке управляемого кода предупреждает о случаях, когда CER требуется расширить с помощью явных вызовов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>, если дополнительные сведения, требуемые для вычисления целевого объекта вызова, известны во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="853ba-106">This MDA warns of cases where a CER might need to be extended by using explicit calls to the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method once the additional information required to compute the call target is known at run time.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="853ba-107">Симптомы</span><span class="sxs-lookup"><span data-stu-id="853ba-107">Symptoms</span></span>  
 <span data-ttu-id="853ba-108">Области CER, которые не выполняются при прерывании потока или при выгрузке домена приложения.</span><span class="sxs-lookup"><span data-stu-id="853ba-108">CERs that do not run when a thread is aborted or an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="853ba-109">Причина</span><span class="sxs-lookup"><span data-stu-id="853ba-109">Cause</span></span>  
 <span data-ttu-id="853ba-110">CER содержит вызов виртуального метода, который не удается подготовить автоматически.</span><span class="sxs-lookup"><span data-stu-id="853ba-110">A CER contains a call to a virtual method that cannot be prepared automatically.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="853ba-111">Решение</span><span class="sxs-lookup"><span data-stu-id="853ba-111">Resolution</span></span>  
 <span data-ttu-id="853ba-112">Следует вызвать <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> для виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="853ba-112">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> for the virtual method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="853ba-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="853ba-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="853ba-114">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="853ba-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="853ba-115">Вывод</span><span class="sxs-lookup"><span data-stu-id="853ba-115">Output</span></span>  
  
```  
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a><span data-ttu-id="853ba-116">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="853ba-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="853ba-117">Пример</span><span class="sxs-lookup"><span data-stu-id="853ba-117">Example</span></span>  
  
```csharp
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of   
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="853ba-118">См. также</span><span class="sxs-lookup"><span data-stu-id="853ba-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="853ba-119">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="853ba-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="853ba-120">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="853ba-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
