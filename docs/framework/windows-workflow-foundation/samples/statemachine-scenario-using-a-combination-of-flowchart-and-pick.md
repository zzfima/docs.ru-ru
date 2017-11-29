---
title: "Сценарий конечного автомата с использованием сочетания действий FlowChart и Pick"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0fb0364310c8780dd41c5369e6b1851dee668d15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a><span data-ttu-id="dd1c7-102">Сценарий конечного автомата с использованием сочетания действий FlowChart и Pick</span><span class="sxs-lookup"><span data-stu-id="dd1c7-102">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>
<span data-ttu-id="dd1c7-103">Этот образец показывает, как реализовать сценарий простого контрольного таймера с помощью сочетания действий <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-103">This sample demonstrates how to implement a simple stopwatch scenario using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span> <span data-ttu-id="dd1c7-104">Для прослушивания событий контрольного таймера используются операции Receive и Send, заданные в действии Pick.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-104">It uses Receive and Send within the Pick activity to listen for stopwatch events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd1c7-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dd1c7-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dd1c7-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd1c7-107">Если этот каталог не существует, перейдите на страницу загрузки, чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd1c7-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd1c7-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a><span data-ttu-id="dd1c7-109">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="dd1c7-109">Sample Details</span></span>  
 <span data-ttu-id="dd1c7-110">В следующей таблице перечислены проекты данного образца.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-110">The following table lists the projects in this sample.</span></span>  
  
|<span data-ttu-id="dd1c7-111">Имя проекта</span><span class="sxs-lookup"><span data-stu-id="dd1c7-111">Project Name</span></span>|<span data-ttu-id="dd1c7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dd1c7-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="dd1c7-113">StopWatchService</span><span class="sxs-lookup"><span data-stu-id="dd1c7-113">StopWatchService</span></span>|<span data-ttu-id="dd1c7-114">Данный проект реализует конечный автомат для образца контрольного таймера, использующий сочетание действий <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-114">This project contains the implementation of a state machine for the stopwatch sample using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span><br /><br /> <span data-ttu-id="dd1c7-115">Действие <xref:System.Activities.Statements.Pick> имеет 3 оператора <xref:System.Activities.Statements.PickBranch> в свойстве <xref:System.Activities.Statements.Pick.Branches%2A>, которые прослушивают события `GetStart`, `GetStop` и `GetOff`.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-115">The <xref:System.Activities.Statements.Pick> activity has 3 <xref:System.Activities.Statements.PickBranch> statements within the <xref:System.Activities.Statements.Pick.Branches%2A> property that listen for `GetStart`, `GetStop` and `GetOff` events.</span></span> <span data-ttu-id="dd1c7-116">В зависимости от входящего события активируются триггеры одной из ветвей, и выполняется соответствующее действие <xref:System.Activities.Statements.PickBranch.Action%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-116">Based on the incoming event, the triggers for one of the branches activate and the corresponding <xref:System.Activities.Statements.PickBranch.Action%2A> is triggered.</span></span> <span data-ttu-id="dd1c7-117">В свойстве <xref:System.Activities.Statements.PickBranch.Action%2A> имеется оператор <xref:System.Activities.Statements.Switch%601>, который определяет допустимость перехода и, если такой переход допустим, свойство `currentState` обновляется до состояния перехода и передается клиенту.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-117">In the <xref:System.Activities.Statements.PickBranch.Action%2A> property, there is a <xref:System.Activities.Statements.Switch%601> statement that evaluates whether the transition is a legitimate transition and if it is, the `currentState` property is updated to the transitioning state and sent to the client.</span></span><br /><br /> <span data-ttu-id="dd1c7-118">Действие <xref:System.Activities.Statements.FlowDecision>, выполняемое в конце <xref:System.Activities.Statements.Flowchart>, осуществляет расчет свойства `currentState`, чтобы определить, достигло ли оно завершающего состояния.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-118">The <xref:System.Activities.Statements.FlowDecision> activity at the end of the <xref:System.Activities.Statements.Flowchart> evaluates the `currentState` property to determine whether the state is terminal.</span></span> <span data-ttu-id="dd1c7-119">Если переход в завершающее состояние осуществлен, рабочий процесс заканчивается. В противном случае управление передается к началу действия <xref:System.Activities.Statements.Pick>, где рабочий процесс будет ожидать наступления следующих событий контрольного таймера.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-119">If it is, the workflow ends; otherwise control loops back to the start of the <xref:System.Activities.Statements.Pick> activity where the workflow waits for more stopwatch events.</span></span>|  
|<span data-ttu-id="dd1c7-120">StopWatchClient</span><span class="sxs-lookup"><span data-stu-id="dd1c7-120">StopWatchClient</span></span>|<span data-ttu-id="dd1c7-121">Представляет собой простое консольное приложение, состоящее из последовательности рабочих процессов, отправляющих различные события контрольного таймера посредством простых сочетаний действий Send и Receive.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-121">This is a simple sequential workflow console application that sends various stopwatch events with simple Send or Receive activity combinations.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dd1c7-122">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="dd1c7-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="dd1c7-123">Откройте файл решения StateMachineWithPick.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd1c7-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open StateMachineWithPick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="dd1c7-124">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="dd1c7-125">Запуск StopWatchService.exe из [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] от имени администратора, щелкнув правой кнопкой мыши файл .exe и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-125">Start the StopWatchService.exe from [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] as an administrator by right clicking the .exe file and selecting **Run as administrator**.</span></span>  
  
    1.  <span data-ttu-id="dd1c7-126">Перейдите в папку StateMachineWithPick\CS\StopWatchService\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-126">Navigate to the StateMachineWithPick\CS\StopWatchService\bin\Debug folder.</span></span>  
  
    2.  <span data-ttu-id="dd1c7-127">Щелкните правой кнопкой мыши файл StopWatchService.exe и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-127">Right-click the StopWatchService.exe file and select **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="dd1c7-128">Запустите клиентское приложение StopWatchClient из [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd1c7-128">Start the StopWatchClient client application from within [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    1.  <span data-ttu-id="dd1c7-129">В **обозревателе решений**выберите **StopWatchClient** проект и щелкните правой кнопкой мыши **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-129">In **Solution Explorer**, select the **StopWatchClient** project and right-click **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="dd1c7-130">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-130">To run the solution, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="dd1c7-131">Перейдите обратно в окно консоли приложения StopWatchService.exe, чтобы наблюдать за переходами состояний.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-131">Switch back to the console window for the StopWatchService.exe to view the state transitions.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd1c7-132">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dd1c7-133">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dd1c7-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd1c7-134">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd1c7-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd1c7-135">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dd1c7-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="see-also"></a><span data-ttu-id="dd1c7-136">См. также</span><span class="sxs-lookup"><span data-stu-id="dd1c7-136">See Also</span></span>
