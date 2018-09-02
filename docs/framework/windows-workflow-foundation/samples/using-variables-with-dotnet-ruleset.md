---
title: Использование переменных с набором правил из .NET Framework 3.5
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 64d47564076e19e152e30b6ab0cb3900ce53cfa1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395158"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="edb90-102">Использование переменных с набором правил из .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="edb90-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="edb90-103">В этом образце демонстрируется создание рабочего процесса, использующего действие <xref:System.Activities.Statements.Interop> для интеграции настраиваемого действия, записанного в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] с применением политики и правил.</span><span class="sxs-lookup"><span data-stu-id="edb90-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="edb90-104">Рабочий процесс передает данные для пользовательского действия, привязывая переменные к свойствам зависимостей, предоставляемым настраиваемым действием.</span><span class="sxs-lookup"><span data-stu-id="edb90-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="edb90-105">Пошаговое руководство по образцу</span><span class="sxs-lookup"><span data-stu-id="edb90-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="edb90-106">Проверка TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="edb90-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="edb90-107">Откройте файл решения InteropWith35RuleSet.sln в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="edb90-107">Using Visual Studio, open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="edb90-108">Откройте TravelRuleSet.cs в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="edb90-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="edb90-109">Последовательное пользовательское действие, содержащее <xref:System.Workflow.Activities.PolicyActivity> отражается на экране.</span><span class="sxs-lookup"><span data-stu-id="edb90-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="edb90-110">Дважды щелкните действие политики DiscountPolicy для просмотра правил.</span><span class="sxs-lookup"><span data-stu-id="edb90-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="edb90-111">Появится редактор правил, показывая правила.</span><span class="sxs-lookup"><span data-stu-id="edb90-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="edb90-112">Щелкните правой кнопкой мыши `DiscountPolicy` и выберите **Просмотр кода** возможность просмотра побочного C# кода для действия.</span><span class="sxs-lookup"><span data-stu-id="edb90-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="edb90-113">Проверьте значения свойства зависимости для `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="edb90-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="edb90-114">Это эквивалентно аргументам в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edb90-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="edb90-115">Дополнительные сведения об аргументах см. в разделе [переменных и аргументов](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="edb90-115">For more information about arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="edb90-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="edb90-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="edb90-117">Это проект последовательного рабочего процесса, использующий действие <xref:System.Activities.Statements.Interop> для интеграции с пользовательским набором правил, создаваемым в проекте `TravelRuleLibrary`.</span><span class="sxs-lookup"><span data-stu-id="edb90-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="edb90-118">Переменные создаются при действии верхнего уровня <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="edb90-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="edb90-119">Действие <xref:System.Activities.Statements.Interop> используется для интеграции с действием `TravelRuleSet`.</span><span class="sxs-lookup"><span data-stu-id="edb90-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="edb90-120">Переменные, объявленные в <xref:System.Activities.Statements.Sequence>, используются для привязки к свойствам зависимости.</span><span class="sxs-lookup"><span data-stu-id="edb90-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="edb90-121">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="edb90-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="edb90-122">Откройте файл решения InteropWith35RuleSet.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edb90-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="edb90-123">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="edb90-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="edb90-124">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="edb90-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="edb90-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="edb90-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="edb90-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="edb90-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="edb90-127">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="edb90-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="edb90-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="edb90-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`