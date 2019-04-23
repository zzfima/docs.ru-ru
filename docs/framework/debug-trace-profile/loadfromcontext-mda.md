---
title: Помощник по отладке управляемого кода loadFromContext
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b2cf06a5ab921f5ae89da4856e8164b6f57db5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098615"
---
# <a name="loadfromcontext-mda"></a><span data-ttu-id="08bf3-102">Помощник по отладке управляемого кода loadFromContext</span><span class="sxs-lookup"><span data-stu-id="08bf3-102">loadFromContext MDA</span></span>
<span data-ttu-id="08bf3-103">Помощник по отладке управляемого кода (MDA) `loadFromContext` активируется при загрузке сборки в контекст `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="08bf3-103">The `loadFromContext` managed debugging assistant (MDA) is activated if an assembly is loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="08bf3-104">Эта ситуация может возникнуть в результате вызова метода <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> или других аналогичных методов.</span><span class="sxs-lookup"><span data-stu-id="08bf3-104">This situation can occur as a result of calling <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or other similar methods.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="08bf3-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="08bf3-105">Symptoms</span></span>  
 <span data-ttu-id="08bf3-106">Использование некоторых методов загрузчика может привести к загрузке сборок в контекст `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="08bf3-106">The use of some loader methods can result in assemblies being loaded in the `LoadFrom` context.</span></span> <span data-ttu-id="08bf3-107">Использование этого контекста может привести к неожиданному поведению при сериализации, приведении типов и разрешении зависимостей.</span><span class="sxs-lookup"><span data-stu-id="08bf3-107">The use of this context can result in unexpected behavior for serialization, casting, and dependency resolution.</span></span> <span data-ttu-id="08bf3-108">Чтобы избежать этих проблем, рекомендуется загружать сборки в контекст `Load`.</span><span class="sxs-lookup"><span data-stu-id="08bf3-108">In general, it is recommended that assemblies be loaded into the `Load` context to avoid these problems.</span></span> <span data-ttu-id="08bf3-109">Без этого помощника по отладке управляемого кода определить, в какой контекст загружена сборка, трудно.</span><span class="sxs-lookup"><span data-stu-id="08bf3-109">It is difficult to determine which context an assembly has been loaded into without this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="08bf3-110">Причина</span><span class="sxs-lookup"><span data-stu-id="08bf3-110">Cause</span></span>  
 <span data-ttu-id="08bf3-111">Как правило, при использовании пути за пределами контекста `Load`, например глобального кэша сборок или свойства <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>, сборка загружается в контекст `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="08bf3-111">Generally, an assembly was loaded into the `LoadFrom` context if it was loaded from a path outside the `Load` context, such as the global assembly cache or the <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="08bf3-112">Решение</span><span class="sxs-lookup"><span data-stu-id="08bf3-112">Resolution</span></span>  
 <span data-ttu-id="08bf3-113">Настройте приложения таким образом, чтобы вызовы <xref:System.Reflection.Assembly.LoadFrom%2A> больше не требовались.</span><span class="sxs-lookup"><span data-stu-id="08bf3-113">Configure applications such that <xref:System.Reflection.Assembly.LoadFrom%2A> calls are no longer needed.</span></span> <span data-ttu-id="08bf3-114">Это можно сделать следующими способами:</span><span class="sxs-lookup"><span data-stu-id="08bf3-114">You can use the following techniques for doing so:</span></span>  
  
-   <span data-ttu-id="08bf3-115">Установите сборки в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="08bf3-115">Install assemblies in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="08bf3-116">Поместите сборки в каталог <xref:System.AppDomainSetup.ApplicationBase%2A> для <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="08bf3-116">Place assemblies in the <xref:System.AppDomainSetup.ApplicationBase%2A> directory for the <xref:System.AppDomain>.</span></span> <span data-ttu-id="08bf3-117">Для домена по умолчанию каталог <xref:System.AppDomainSetup.ApplicationBase%2A> содержит исполняемый файл, который запустил процесс.</span><span class="sxs-lookup"><span data-stu-id="08bf3-117">In the case of the default domain, the <xref:System.AppDomainSetup.ApplicationBase%2A> directory is the one that contains the executable file that started the process.</span></span> <span data-ttu-id="08bf3-118">Если перемещать сборку неудобно, также может потребоваться создать новый <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="08bf3-118">This might also require creating a new <xref:System.AppDomain> if it is not convenient to move the assembly.</span></span>  
  
-   <span data-ttu-id="08bf3-119">Если зависимые сборки находятся в дочерних папках по отношению к исполняемому файлу, добавьте путь проверки в файл конфигурации приложения (.config) или во вторичные домены приложения.</span><span class="sxs-lookup"><span data-stu-id="08bf3-119">Add a probing path to your application configuration (.config) file or to secondary  application domains if dependent assemblies are in child directories relative to the executable.</span></span>  
  
 <span data-ttu-id="08bf3-120">В каждом случае можно изменить код, включив в него метод <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08bf3-120">In each case, the code can be changed to use the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="08bf3-121">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="08bf3-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="08bf3-122">Помощник по отладке управляемого кода не оказывает никакого воздействия на общеязыковую среду выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="08bf3-122">The MDA does not have any effect on the CLR.</span></span> <span data-ttu-id="08bf3-123">В качестве результата запроса на загрузку он возвращает используемый контекст.</span><span class="sxs-lookup"><span data-stu-id="08bf3-123">It reports the context that was used as a result of a load request.</span></span>  
  
## <a name="output"></a><span data-ttu-id="08bf3-124">Вывод</span><span class="sxs-lookup"><span data-stu-id="08bf3-124">Output</span></span>  
 <span data-ttu-id="08bf3-125">Помощник по отладке управляемого кода сообщает, что сборка была загружена в контекст `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="08bf3-125">The MDA reports that the assembly was loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="08bf3-126">В выводе указаны простое имя сборки и путь к ней.</span><span class="sxs-lookup"><span data-stu-id="08bf3-126">It specifies the simple name of the assembly and the path.</span></span> <span data-ttu-id="08bf3-127">В выводе также указаны рекомендации, позволяющие избежать использования контекста `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="08bf3-127">It also suggests mitigations to avoid using the `LoadFrom` context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="08bf3-128">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="08bf3-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="08bf3-129">Пример</span><span class="sxs-lookup"><span data-stu-id="08bf3-129">Example</span></span>  
 <span data-ttu-id="08bf3-130">В следующем примере кода показана ситуация, которая может привести к запуску помощника по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="08bf3-130">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="08bf3-131">См. также</span><span class="sxs-lookup"><span data-stu-id="08bf3-131">See also</span></span>

- [<span data-ttu-id="08bf3-132">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="08bf3-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
