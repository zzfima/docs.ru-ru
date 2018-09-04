---
title: Параллельное действие ForEach с ограничением
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 7149e6db8992bff5b436ffae4a77d985ec255986
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564909"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="cbe21-102">Параллельное действие ForEach с ограничением</span><span class="sxs-lookup"><span data-stu-id="cbe21-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="cbe21-103">`ThrottleParallelForEach` Аналогично действию <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` действия, за одним исключением, позволяет настроить фактор одновременности для ограничения число одновременно выполняющихся ветвей.</span><span class="sxs-lookup"><span data-stu-id="cbe21-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="cbe21-104">Действие `ThrottleParallelForEach` является производным от действия <xref:System.Activities.NativeActivity>, поскольку оно должно планировать другие действия (дочерние действия), что можно сделать только через класс <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="cbe21-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="cbe21-105">Проекты</span><span class="sxs-lookup"><span data-stu-id="cbe21-105">Projects</span></span>  
  
|<span data-ttu-id="cbe21-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="cbe21-106">**ProjectName**</span></span>|<span data-ttu-id="cbe21-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cbe21-107">**Description**</span></span>|<span data-ttu-id="cbe21-108">**Основные файлы**</span><span class="sxs-lookup"><span data-stu-id="cbe21-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="cbe21-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="cbe21-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="cbe21-110">Содержит действие `ThrottledParallelForEach` и его конструктор.</span><span class="sxs-lookup"><span data-stu-id="cbe21-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="cbe21-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="cbe21-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="cbe21-112">Определение действия `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="cbe21-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="cbe21-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="cbe21-113">CodeTestClient</span></span>|<span data-ttu-id="cbe21-114">Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием `ThrottledParallelForEach` при помощи императивного кода.</span><span class="sxs-lookup"><span data-stu-id="cbe21-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="cbe21-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="cbe21-115">Program.cs</span></span><br /><br /> <span data-ttu-id="cbe21-116">Определяет и выполняет экземпляр образца рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cbe21-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="cbe21-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="cbe21-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="cbe21-118">Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ThrottledParallelForEach.sln.</span><span class="sxs-lookup"><span data-stu-id="cbe21-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="cbe21-119">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="cbe21-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="cbe21-120">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="cbe21-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cbe21-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cbe21-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbe21-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cbe21-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cbe21-123">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="cbe21-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbe21-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cbe21-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`