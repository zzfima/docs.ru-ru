---
title: jitCompilationStart MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fd520392ca7f6bb97ac11d868db7a0df9a32d5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="4fd0a-102">jitCompilationStart MDA</span><span class="sxs-lookup"><span data-stu-id="4fd0a-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="4fd0a-103">Помощник по отладке управляемого кода (MDA) `jitCompilationStart` активируется, чтобы сообщить о том, что JIT-компилятор начал компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4fd0a-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="4fd0a-104">Symptoms</span></span>  
 <span data-ttu-id="4fd0a-105">Размер рабочего набора для программы, уже находящейся в формате образа в машинном коде, увеличивается, так как в процесс загружается библиотека mscorjit.dll.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4fd0a-106">Причина</span><span class="sxs-lookup"><span data-stu-id="4fd0a-106">Cause</span></span>  
 <span data-ttu-id="4fd0a-107">Не все сборки, от которых зависит программа, были сгенерированы в собственном формате, либо те сборки, которые были сгенерированы в этом формате, не были правильно зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4fd0a-108">Решение</span><span class="sxs-lookup"><span data-stu-id="4fd0a-108">Resolution</span></span>  
 <span data-ttu-id="4fd0a-109">Включение этого помощника по отладке управляемого кода позволяет определить, какие функции были скомпилированы посредством JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="4fd0a-110">Следует определить, была ли сборка, содержащая функцию, сгенерирована в собственном формате и правильно зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4fd0a-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="4fd0a-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="4fd0a-112">Этот помощник по отладке управляемого кода записывает сообщение непосредственно перед компиляцией метода с помощью JIT-компилятора, поэтому включение этого помощника оказывает значительное влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="4fd0a-113">Обратите внимание, что если метод является встроенным, этот помощник по отладке управляемого кода не будет создавать отдельное сообщение.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4fd0a-114">Вывод</span><span class="sxs-lookup"><span data-stu-id="4fd0a-114">Output</span></span>  
 <span data-ttu-id="4fd0a-115">Ниже приведен пример выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-115">The following code sample shows sample output.</span></span> <span data-ttu-id="4fd0a-116">В этом случае видно, что в сборке Test метод m класса ns2.CO был скомпилирован посредством JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="4fd0a-117">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4fd0a-117">Configuration</span></span>  
 <span data-ttu-id="4fd0a-118">Приведенный ниже файл конфигурации содержит различные фильтры, которые можно применять, чтобы отфильтровать методы, о которых будет сообщено при их первой JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="4fd0a-119">Можно указать, что необходимо сообщать о всех методах, установив значение атрибута имени равным *.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-119">You can specify that all methods be reported by setting the value of the name attribute to *.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="4fd0a-120">Пример</span><span class="sxs-lookup"><span data-stu-id="4fd0a-120">Example</span></span>  
 <span data-ttu-id="4fd0a-121">Приведенный ниже пример кода предназначен для использования с предыдущим файлом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4fd0a-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```  
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fd0a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4fd0a-122">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="4fd0a-123">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="4fd0a-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="4fd0a-124">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="4fd0a-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
