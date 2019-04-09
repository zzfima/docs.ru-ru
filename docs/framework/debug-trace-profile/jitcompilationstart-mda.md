---
title: jitCompilationStart MDA
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62064286fecc4736f39ad790f0fd7f0e6d84b149
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162349"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="972ac-102">jitCompilationStart MDA</span><span class="sxs-lookup"><span data-stu-id="972ac-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="972ac-103">Помощник по отладке управляемого кода (MDA) `jitCompilationStart` активируется, чтобы сообщить о том, что JIT-компилятор начал компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="972ac-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="972ac-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="972ac-104">Symptoms</span></span>  
 <span data-ttu-id="972ac-105">Размер рабочего набора для программы, уже находящейся в формате образа в машинном коде, увеличивается, так как в процесс загружается библиотека mscorjit.dll.</span><span class="sxs-lookup"><span data-stu-id="972ac-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="972ac-106">Причина</span><span class="sxs-lookup"><span data-stu-id="972ac-106">Cause</span></span>  
 <span data-ttu-id="972ac-107">Не все сборки, от которых зависит программа, были сгенерированы в собственном формате, либо те сборки, которые были сгенерированы в этом формате, не были правильно зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="972ac-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="972ac-108">Решение</span><span class="sxs-lookup"><span data-stu-id="972ac-108">Resolution</span></span>  
 <span data-ttu-id="972ac-109">Включение этого помощника по отладке управляемого кода позволяет определить, какие функции были скомпилированы посредством JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="972ac-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="972ac-110">Следует определить, была ли сборка, содержащая функцию, сгенерирована в собственном формате и правильно зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="972ac-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="972ac-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="972ac-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="972ac-112">Этот помощник по отладке управляемого кода записывает сообщение непосредственно перед компиляцией метода с помощью JIT-компилятора, поэтому включение этого помощника оказывает значительное влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="972ac-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="972ac-113">Обратите внимание, что если метод является встроенным, этот помощник по отладке управляемого кода не будет создавать отдельное сообщение.</span><span class="sxs-lookup"><span data-stu-id="972ac-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="972ac-114">Вывод</span><span class="sxs-lookup"><span data-stu-id="972ac-114">Output</span></span>  
 <span data-ttu-id="972ac-115">Ниже приведен пример выходных данных.</span><span class="sxs-lookup"><span data-stu-id="972ac-115">The following code sample shows sample output.</span></span> <span data-ttu-id="972ac-116">В этом случае видно, что в сборке Test метод m класса ns2.CO был скомпилирован посредством JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="972ac-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="972ac-117">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="972ac-117">Configuration</span></span>  
 <span data-ttu-id="972ac-118">Приведенный ниже файл конфигурации содержит различные фильтры, которые можно применять, чтобы отфильтровать методы, о которых будет сообщено при их первой JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="972ac-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="972ac-119">Можно указать, что все методы возвратить значение атрибута имени для \*.</span><span class="sxs-lookup"><span data-stu-id="972ac-119">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="972ac-120">Пример</span><span class="sxs-lookup"><span data-stu-id="972ac-120">Example</span></span>  
 <span data-ttu-id="972ac-121">Приведенный ниже пример кода предназначен для использования с предыдущим файлом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="972ac-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="972ac-122">См. также</span><span class="sxs-lookup"><span data-stu-id="972ac-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="972ac-123">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="972ac-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="972ac-124">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="972ac-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
