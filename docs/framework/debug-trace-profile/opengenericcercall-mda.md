---
title: openGenericCERCall MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: de1735103314dfedbabe27623f579ce2c1e728af
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217268"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="863ee-102">openGenericCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="863ee-102">openGenericCERCall MDA</span></span>

<span data-ttu-id="863ee-103">Помощник по отладке управляемого кода `openGenericCERCall` активируется, чтобы предупредить о том, что граф области ограниченного выполнения (CER) с переменными универсального типа в корневом методе обрабатывается во время JIT-компиляции или генерации образа в машинном коде и при этом как минимум одна из переменных универсального типа представляет собой тип ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="863ee-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="863ee-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="863ee-104">Symptoms</span></span>

<span data-ttu-id="863ee-105">Код в области ограниченного выполнения не выполняется при прерывании потока или при выгрузке домена приложения.</span><span class="sxs-lookup"><span data-stu-id="863ee-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="863ee-106">Причина</span><span class="sxs-lookup"><span data-stu-id="863ee-106">Cause</span></span>

<span data-ttu-id="863ee-107">Во время JIT-компиляции создание экземпляра типа ссылки на объект носит исключительно репрезентативный характер, поскольку полученный код будет общим, а каждая переменная типа ссылки на объект может быть любого типа ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="863ee-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="863ee-108">Это позволяет предотвратить заблаговременную подготовку некоторых ресурсов времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="863ee-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="863ee-109">В частности, методы с переменными универсального типа могут отложенным образом выделять ресурсы в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="863ee-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="863ee-110">Это записи универсального словаря.</span><span class="sxs-lookup"><span data-stu-id="863ee-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="863ee-111">Например, для инструкции `List<T> list = new List<T>();`, где `T` является переменной универсального типа, среда выполнения должна выполнять поиск и, возможно, создать точное создание экземпляра во время выполнения, например `List<Object>, List<String>`и т. д.</span><span class="sxs-lookup"><span data-stu-id="863ee-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="863ee-112">Этот процесс может завершаться сбоем по целому ряду причин, которые разработчик не может контролировать, например из-за нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="863ee-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="863ee-113">Этот помощник по отладке управляемого кода следует активировать только во время JIT-компиляции, а не при создании точного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="863ee-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="863ee-114">Как правило, активация этого помощника по отладке управляемого кода вызвана сбоем области ограниченного выполнения для поврежденных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="863ee-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="863ee-115">Фактически среда выполнения не пытается реализовать область ограниченного выполнения в ситуации, в которой активируется этот помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="863ee-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="863ee-116">Если разработчик использует общий экземпляр среды ограниченного выполнения, ошибки JIT-компиляции, ошибки загрузки универсальных типов или прерывания потоков в предполагаемой области ограниченного выполнения не перехватываются.</span><span class="sxs-lookup"><span data-stu-id="863ee-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="863ee-117">Решение</span><span class="sxs-lookup"><span data-stu-id="863ee-117">Resolution</span></span>

<span data-ttu-id="863ee-118">Не используйте переменные универсального типа, которые имеют тип ссылки на объект, в методах, которые могут содержать область ограниченного выполнения.</span><span class="sxs-lookup"><span data-stu-id="863ee-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="863ee-119">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="863ee-119">Effect on the Runtime</span></span>

<span data-ttu-id="863ee-120">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="863ee-120">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="863ee-121">Вывод</span><span class="sxs-lookup"><span data-stu-id="863ee-121">Output</span></span>

<span data-ttu-id="863ee-122">Ниже приведен пример выходных данных из этого помощника по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="863ee-122">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution. 
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="863ee-123">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="863ee-123">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="863ee-124">Пример</span><span class="sxs-lookup"><span data-stu-id="863ee-124">Example</span></span>

<span data-ttu-id="863ee-125">Код в области ограниченного выполнения не выполняется.</span><span class="sxs-lookup"><span data-stu-id="863ee-125">The CER code is not executed.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The 
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="863ee-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="863ee-126">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="863ee-127">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="863ee-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
