---
title: memberInfoCacheCreation MDA
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90f59f4d593a8aa077a6710cc0f5c1747ac1a3ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103770"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="35c22-102">memberInfoCacheCreation MDA</span><span class="sxs-lookup"><span data-stu-id="35c22-102">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="35c22-103">Помощник по отладке управляемого кода (MDA) `memberInfoCacheCreation` запускается при создании кэша <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="35c22-103">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="35c22-104">Это явный признак программы, в которой используются ресурсоемкие функции отражения.</span><span class="sxs-lookup"><span data-stu-id="35c22-104">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="35c22-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="35c22-105">Symptoms</span></span>  
 <span data-ttu-id="35c22-106">Рабочий набор программы увеличивается, так как в программе используются ресурсоемкие функции отражения.</span><span class="sxs-lookup"><span data-stu-id="35c22-106">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="35c22-107">Причина</span><span class="sxs-lookup"><span data-stu-id="35c22-107">Cause</span></span>  
 <span data-ttu-id="35c22-108">Операции отражения, которые включают объекты <xref:System.Reflection.MemberInfo>, считаются ресурсоемкими, так как они должны считывать метаданные, которые хранятся на "холодных" страницах. Обычно эти операции означают, что в программе используется какой-либо сценарий позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="35c22-108">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="35c22-109">Решение</span><span class="sxs-lookup"><span data-stu-id="35c22-109">Resolution</span></span>  
 <span data-ttu-id="35c22-110">Чтобы определить, в какой точке программы используется отражение, можете включить этот помощник по отладке управляемого кода и запустить код в отладчике или подключиться к отладчику при запуске помощника по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="35c22-110">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="35c22-111">В отладчике появится трассировка стека, в которой будет показано место создания кэша <xref:System.Reflection.MemberInfo>. Так вы сможете определить, в какой точке программы используется отражение.</span><span class="sxs-lookup"><span data-stu-id="35c22-111">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="35c22-112">Способ решения задачи зависит назначения кода.</span><span class="sxs-lookup"><span data-stu-id="35c22-112">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="35c22-113">Этот помощник по отладке управляемого кода предупреждает о том, что в программе используется сценарий позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="35c22-113">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="35c22-114">Вы сможете решить, следует ли заменить его на сценарий раннего связывания или сохранить сценарий позднего связывания, так как он обладает достаточной производительностью.</span><span class="sxs-lookup"><span data-stu-id="35c22-114">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="35c22-115">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="35c22-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="35c22-116">Этот помощник по отладке управляемого кода запускается каждый раз при создании кэша <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="35c22-116">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="35c22-117">Влияние на производительность незначительно.</span><span class="sxs-lookup"><span data-stu-id="35c22-117">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="35c22-118">Вывод</span><span class="sxs-lookup"><span data-stu-id="35c22-118">Output</span></span>  
 <span data-ttu-id="35c22-119">Помощник по отладке управляемого кода выводит сообщение о создании кэша <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="35c22-119">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="35c22-120">Используйте отладчик, чтобы получить трассировку стека, в которой будет показано, где в программе используется отражение.</span><span class="sxs-lookup"><span data-stu-id="35c22-120">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="35c22-121">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="35c22-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="35c22-122">Пример</span><span class="sxs-lookup"><span data-stu-id="35c22-122">Example</span></span>  
 <span data-ttu-id="35c22-123">При выполнении кода в этом примере будет запущен помощник по отладке управляемого кода `memberInfoCacheCreation`.</span><span class="sxs-lookup"><span data-stu-id="35c22-123">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="35c22-124">См. также</span><span class="sxs-lookup"><span data-stu-id="35c22-124">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="35c22-125">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="35c22-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
