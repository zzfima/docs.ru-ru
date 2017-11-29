---
title: "Использование переменных с набором правил из .NET Framework 3.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9b5cc982aaad92258102b313d8fc19a9ff1521a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="ab0b6-102">Использование переменных с набором правил из .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="ab0b6-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="ab0b6-103">В этом образце демонстрируется создание рабочего процесса, использующего действие <xref:System.Activities.Statements.Interop> для интеграции настраиваемого действия, записанного в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] с применением политики и правил.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="ab0b6-104">Рабочий процесс передает данные для пользовательского действия, привязывая переменные к свойствам зависимостей, предоставляемым настраиваемым действием.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="ab0b6-105">Пошаговое руководство по образцу</span><span class="sxs-lookup"><span data-stu-id="ab0b6-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="ab0b6-106">Проверка TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="ab0b6-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="ab0b6-107">Откройте файл решения InteropWith35RuleSet.sln в среде [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab0b6-107">Using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ab0b6-108">Откройте TravelRuleSet.cs в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="ab0b6-109">Последовательное пользовательское действие, содержащее <xref:System.Workflow.Activities.PolicyActivity> отражается на экране.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="ab0b6-110">Дважды щелкните действие политики DiscountPolicy для просмотра правил.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="ab0b6-111">Появится редактор правил, показывая правила.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="ab0b6-112">Щелкните правой кнопкой мыши `DiscountPolicy` и выберите **Просмотр кода** для просмотра побочного C# кода для действия.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="ab0b6-113">Проверьте значения свойства зависимости для `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="ab0b6-114">Это эквивалентно аргументам в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab0b6-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ab0b6-115">аргументы, в разделе [переменных и аргументов](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="ab0b6-115"> arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="ab0b6-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="ab0b6-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="ab0b6-117">Это проект последовательного рабочего процесса, использующий действие <xref:System.Activities.Statements.Interop> для интеграции с пользовательским набором правил, создаваемым в проекте `TravelRuleLibrary`.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="ab0b6-118">Переменные создаются при действии верхнего уровня <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="ab0b6-119">Действие <xref:System.Activities.Statements.Interop> используется для интеграции с действием `TravelRuleSet`.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="ab0b6-120">Переменные, объявленные в <xref:System.Activities.Statements.Sequence>, используются для привязки к свойствам зависимости.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="ab0b6-121">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="ab0b6-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="ab0b6-122">Откройте файл решения InteropWith35RuleSet.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab0b6-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ab0b6-123">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ab0b6-124">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab0b6-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ab0b6-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ab0b6-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ab0b6-127">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab0b6-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab0b6-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ab0b6-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`  
  
## <a name="see-also"></a><span data-ttu-id="ab0b6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ab0b6-129">See Also</span></span>
