---
title: "Сочетание базовых действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 047948552471b33af8690b526db7c416e87f897a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="basic-activity-composition"></a><span data-ttu-id="8cb63-102">Сочетание базовых действий</span><span class="sxs-lookup"><span data-stu-id="8cb63-102">Basic Activity Composition</span></span>
<span data-ttu-id="8cb63-103">В этом образце показывается создание пользовательских и предоставляемых системой действий для построения других пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="8cb63-103">This sample demonstrates how to compose custom activities and system-provided activities to build more custom activities.</span></span>  
  
 <span data-ttu-id="8cb63-104">Рабочий процесс, использующий действие «Survey», планирует действие «Survey» со списком вопросов, а затем выводит полученные ответы.</span><span class="sxs-lookup"><span data-stu-id="8cb63-104">The workflow using the Survey activity schedules the Survey with a list of questions, and then outputs the responses received.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="8cb63-105">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="8cb63-105">Sample Details</span></span>  
 <span data-ttu-id="8cb63-106">В данном образце используются три пользовательских действия.</span><span class="sxs-lookup"><span data-stu-id="8cb63-106">This sample uses three custom activities.</span></span> <span data-ttu-id="8cb63-107">`ReadLine`— Это простой <xref:System.Activities.NativeActivity> \<строка >, создающего <xref:System.Activities.Bookmark> по расписанию, а затем устанавливает `Return` <xref:System.Activities.OutArgument%601> для значения, которое <xref:System.Activities.Bookmark> возобновляется.</span><span class="sxs-lookup"><span data-stu-id="8cb63-107">`ReadLine` is a simple <xref:System.Activities.NativeActivity>\<string> that creates a <xref:System.Activities.Bookmark> when scheduled, and then sets the `Return`<xref:System.Activities.OutArgument%601> to the value with which the <xref:System.Activities.Bookmark> is resumed.</span></span> <span data-ttu-id="8cb63-108">`Prompt`— <xref:System.Activities.Activity%601> \<строка >, принимающий <xref:System.Activities.InArgument%601>< строка\> с именем `Text` и возвращает пользовательский ответ в `Result` <xref:System.Activities.OutArgument%601> \<строки >.</span><span class="sxs-lookup"><span data-stu-id="8cb63-108">`Prompt` is an <xref:System.Activities.Activity%601>\<string> that takes an <xref:System.Activities.InArgument%601><string\> named `Text` and returns the users response in the `Result`<xref:System.Activities.OutArgument%601>\<string>.</span></span> <span data-ttu-id="8cb63-109">Действие `Prompt` использует действия <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.WriteLine>, поставляемые совместно с платформой .NET Framework, а также содержит пользовательское действие `ReadLine` для получения ввода пользователя.</span><span class="sxs-lookup"><span data-stu-id="8cb63-109">The `Prompt` activity uses the <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.WriteLine> activities that ship as part of the .NET Framework, and also incorporates the custom `ReadLine` activity for getting user input.</span></span> <span data-ttu-id="8cb63-110">Последним пользовательским действием является действие `Survey`.</span><span class="sxs-lookup"><span data-stu-id="8cb63-110">The last custom activity is the `Survey` activity.</span></span> <span data-ttu-id="8cb63-111">Это <xref:System.Activities.Activity>< ICollection\<строка >>.</span><span class="sxs-lookup"><span data-stu-id="8cb63-111">It is an <xref:System.Activities.Activity><ICollection\<string>>.</span></span>  <span data-ttu-id="8cb63-112">Действие принимает <xref:System.Activities.InArgument%601>< IEnumerable < строка\>> с именем `Questions` и заполняет `Result` выходного аргумента с ответами.</span><span class="sxs-lookup"><span data-stu-id="8cb63-112">This activity takes an <xref:System.Activities.InArgument%601><IEnumerable<string\>> named `Questions` and populates the `Result` out argument with the responses.</span></span> <span data-ttu-id="8cb63-113">Действие `Survey` использует действия <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.AddToCollection%601>, поставляемые совместно с платформой .NET Framework, а также использует действие `Prompt` для задания вопросов из опроса и получения ответов.</span><span class="sxs-lookup"><span data-stu-id="8cb63-113">The `Survey` activity uses <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.AddToCollection%601> from the .NET Framework and employs the `Prompt` activity for asking the survey questions and getting responses.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8cb63-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="8cb63-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8cb63-115">Откройте **BasicActivityComposition.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cb63-115">Open the **BasicActivityComposition.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8cb63-116">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="8cb63-116">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8cb63-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8cb63-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8cb63-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8cb63-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8cb63-119">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8cb63-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8cb63-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8cb63-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`