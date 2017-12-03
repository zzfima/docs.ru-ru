---
title: "Использование действия Pick"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18c8af9717cb03bd262ceb0a62c91dbc778071c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="92a48-102">Использование действия Pick</span><span class="sxs-lookup"><span data-stu-id="92a48-102">Using the Pick Activity</span></span>
<span data-ttu-id="92a48-103">Этот образец демонстрирует применение действия <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="92a48-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 <span data-ttu-id="92a48-104">Действие <xref:System.Activities.Statements.Pick> обеспечивает моделирование потока управления на основе событий.</span><span class="sxs-lookup"><span data-stu-id="92a48-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="92a48-105">Поведение действия аналогично поведению оператора C# `switch`, выполняющего только одну из ветвей оператора `switch`.</span><span class="sxs-lookup"><span data-stu-id="92a48-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="92a48-106">В отличие от оператора `switch`, который выполняет ветвь в зависимости от значения, действие <xref:System.Activities.Statements.Pick> выполняет ветвь в зависимости от того, как было завершено действие.</span><span class="sxs-lookup"><span data-stu-id="92a48-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>  
  
 <span data-ttu-id="92a48-107">Этот образец предлагает пользователю ввести свое имя в строке консоли за отведенный для этого период времени.</span><span class="sxs-lookup"><span data-stu-id="92a48-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="92a48-108">Действие <xref:System.Activities.Statements.Pick> в образце имеет две ветви, которые выполняются или не выполняются в зависимости от того, ввел или не ввел пользователь свое имя за отведенные для этого 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="92a48-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="92a48-109">Если пользователь успеет ввести имя в течение 5 секунд, будет выполнена первая ветвь, содержащая пользовательское действие `ReadLine`. В противном случае будет выполнена другая ветвь, содержащая действие <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="92a48-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="92a48-110">После ввода в консоли имени пользователя это имя будет выведено на экран консоли.</span><span class="sxs-lookup"><span data-stu-id="92a48-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="92a48-111">Если в течение 5 секунд ввод не был осуществлен, время ожидания операции истечет и операция будет завершена.</span><span class="sxs-lookup"><span data-stu-id="92a48-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="92a48-112">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="92a48-112">Demonstrates</span></span>  
 <span data-ttu-id="92a48-113">Действие <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="92a48-113"><xref:System.Activities.Statements.Pick> activity.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="92a48-114">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="92a48-114">Discussion</span></span>  
 <span data-ttu-id="92a48-115">В этом образце приведены образцы рабочего процесса, создаваемого в конструкторе, и кодированного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="92a48-115">The sample includes a Designer workflow and coded workflow.</span></span>  
  
 <span data-ttu-id="92a48-116">Рабочий процесс, созданный с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="92a48-116">Designer Workflow</span></span>  
 <span data-ttu-id="92a48-117">Версия образца, созданная с помощью конструктора, показывает, как создавать рабочий процесс в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="92a48-117">The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="92a48-118">Включаются следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="92a48-118">The following files are included:</span></span>  
  
-   <span data-ttu-id="92a48-119">Program.cs: содержит функцию `Main`, выполняющую образец рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="92a48-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="92a48-120">ReadString.cs: настраиваемое действие, считывающее входные данные с консоли.</span><span class="sxs-lookup"><span data-stu-id="92a48-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
-   <span data-ttu-id="92a48-121">Sequence1.xaml: рабочий процесс, созданный с помощью конструктора, использующего действие Pick.</span><span class="sxs-lookup"><span data-stu-id="92a48-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>  
  
 <span data-ttu-id="92a48-122">Кодированный рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="92a48-122">Coded Workflow</span></span>  
 <span data-ttu-id="92a48-123">Кодированная версия образца, показывающая, как создавать рабочий процесс в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="92a48-123">The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="92a48-124">Включаются следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="92a48-124">The following files are included:</span></span>  
  
-   <span data-ttu-id="92a48-125">Program.cs: содержит функцию `Main`, выполняющую образец рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="92a48-125">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="92a48-126">ReadString.cs: настраиваемое действие, считывающее входные данные с консоли.</span><span class="sxs-lookup"><span data-stu-id="92a48-126">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="92a48-127">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="92a48-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="92a48-128">Откройте файл решения Pick.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92a48-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Pick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="92a48-129">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="92a48-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="92a48-130">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="92a48-130">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="92a48-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="92a48-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="92a48-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="92a48-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="92a48-133">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92a48-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="92a48-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="92a48-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`