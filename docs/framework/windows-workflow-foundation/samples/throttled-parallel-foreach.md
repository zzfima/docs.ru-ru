---
title: "Параллельное действие ForEach с ограничением"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b8811327fee8eb2ca3b2ba87d54a0014b20673a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="b4f17-102">Параллельное действие ForEach с ограничением</span><span class="sxs-lookup"><span data-stu-id="b4f17-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="b4f17-103">`ThrottleParallelForEach` Действия аналогична <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` действия, за одним исключением, позволяет настроить коэффициент распараллеливания для ограничения количества одновременно выполняющихся ветвей.</span><span class="sxs-lookup"><span data-stu-id="b4f17-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="b4f17-104">Действие `ThrottleParallelForEach` является производным от действия <xref:System.Activities.NativeActivity>, поскольку оно должно планировать другие действия (дочерние действия), что можно сделать только через класс <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="b4f17-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="b4f17-105">Проекты</span><span class="sxs-lookup"><span data-stu-id="b4f17-105">Projects</span></span>  
  
|<span data-ttu-id="b4f17-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="b4f17-106">**ProjectName**</span></span>|<span data-ttu-id="b4f17-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b4f17-107">**Description**</span></span>|<span data-ttu-id="b4f17-108">**Основные файлы**</span><span class="sxs-lookup"><span data-stu-id="b4f17-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="b4f17-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="b4f17-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="b4f17-110">Содержит действие `ThrottledParallelForEach` и его конструктор.</span><span class="sxs-lookup"><span data-stu-id="b4f17-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="b4f17-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="b4f17-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="b4f17-112">Определение действия `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="b4f17-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="b4f17-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="b4f17-113">CodeTestClient</span></span>|<span data-ttu-id="b4f17-114">Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием `ThrottledParallelForEach` при помощи императивного кода.</span><span class="sxs-lookup"><span data-stu-id="b4f17-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="b4f17-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="b4f17-115">Program.cs</span></span><br /><br /> <span data-ttu-id="b4f17-116">Определяет и выполняет экземпляр образца рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b4f17-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b4f17-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b4f17-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="b4f17-118">Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ThrottledParallelForEach.sln.</span><span class="sxs-lookup"><span data-stu-id="b4f17-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="b4f17-119">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b4f17-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b4f17-120">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="b4f17-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4f17-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b4f17-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b4f17-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b4f17-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b4f17-123">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4f17-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b4f17-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b4f17-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`