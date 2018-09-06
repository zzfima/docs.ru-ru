---
title: Свойства выполнения
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 4906c2ad11c8b5822764435d2b39a5b51f2673ba
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748198"
---
# <a name="execution-properties"></a><span data-ttu-id="63243-102">Свойства выполнения</span><span class="sxs-lookup"><span data-stu-id="63243-102">Execution Properties</span></span>
<span data-ttu-id="63243-103">В этом образце показано, как определить и использовать свойство выполнения в настраиваемом действии.</span><span class="sxs-lookup"><span data-stu-id="63243-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="63243-104">В этом примере свойство выполнения определяет цвет переднего плана консоли.</span><span class="sxs-lookup"><span data-stu-id="63243-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="63243-105">Рабочий процесс в примере показывает, как разные логические пути выполнения (ответвления действия <xref:System.Activities.Statements.Parallel>) могут поддерживать различные цвета консоли, несмотря на поочередное исполнение действий (по всем ответвлениям действия <xref:System.Activities.Statements.Parallel>).</span><span class="sxs-lookup"><span data-stu-id="63243-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="63243-106">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="63243-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="63243-107">Откройте образец решения ExecutionProperties.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63243-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="63243-108">При попытке просмотра ThreeColors.xaml до построения решения произойдет ошибка, поскольку применяемые пользовательские действия должны быть построены одновременно с решением.</span><span class="sxs-lookup"><span data-stu-id="63243-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="63243-109">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="63243-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63243-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="63243-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="63243-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="63243-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="63243-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="63243-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="63243-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="63243-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`