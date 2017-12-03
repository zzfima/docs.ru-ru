---
title: "Проверка внешнего действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ebc79fa582a32ccc252e6c22b9b223870da7e44
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="external-activity-validation"></a><span data-ttu-id="dd945-102">Проверка внешнего действия</span><span class="sxs-lookup"><span data-stu-id="dd945-102">External Activity Validation</span></span>
<span data-ttu-id="dd945-103">В этом образце показано, как добавить логику проверки во встроенное действие, созданное другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="dd945-103">This sample shows how to add validation logic to a built-in activity that you are not the author of.</span></span> <span data-ttu-id="dd945-104">Логика проверки включает принудительное обеспечение для всех свойств <xref:System.Activities.Statements.If>, входящих в рабочий процесс, установки либо свойства <xref:System.Activities.Statements.If.Then%2A>, либо свойства <xref:System.Activities.Statements.If.Else%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd945-104">The validation logic consists of enforcing that all <xref:System.Activities.Statements.If> activities present in the workflow either have their <xref:System.Activities.Statements.If.Then%2A> property set or their <xref:System.Activities.Statements.If.Else%2A> property set.</span></span> <span data-ttu-id="dd945-105">Кроме того, логика проверки включает проверку наличия у всех действий <xref:System.Activities.Statements.Pick>, присутствующих в рабочем процессе, нескольких ветвей. В противном случае создается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="dd945-105">Also, the validation logic includes checking that all <xref:System.Activities.Statements.Pick> activities present in the workflow have more than one branch, and if that is not the case, a warning is generated.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="dd945-106">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="dd945-106">Sample details</span></span>  
 <span data-ttu-id="dd945-107">В данном образце создается рабочий процесс с экземпляром каждого подлежащего проверке действия: действия <xref:System.Activities.Statements.If> и действия <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="dd945-107">This sample creates a workflow with an instance of each activity to validate: the <xref:System.Activities.Statements.If> activity and the <xref:System.Activities.Statements.Pick> activity.</span></span> <span data-ttu-id="dd945-108">Для каждого вида поведения проверки создается объект <xref:System.Activities.Validation.Constraint>.</span><span class="sxs-lookup"><span data-stu-id="dd945-108">A <xref:System.Activities.Validation.Constraint> is created for each validation behavior.</span></span> <span data-ttu-id="dd945-109">В этом образце создаются ограничения `ConstraintError_IfShouldHaveThenOrElse` и `ConstraintWarning_PickHasOneBranch`.</span><span class="sxs-lookup"><span data-stu-id="dd945-109">The constraints created in this sample are `ConstraintError_IfShouldHaveThenOrElse` and `ConstraintWarning_PickHasOneBranch`.</span></span> <span data-ttu-id="dd945-110">Далее эти ограничения добавляются в коллекцию `AdditionalConstraints` экземпляра <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="dd945-110">Next, these constraints are added to the `AdditionalConstraints` collection of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="dd945-111">Наконец, для проверки действий в рабочем процессе вызывается метод `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> служб <xref:System.Activities.Validation.ActivityValidationServices>, а результаты проверки выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="dd945-111">Finally, the `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method of <xref:System.Activities.Validation.ActivityValidationServices> is called to validate the activities in the workflow and the validation results are printed out to the console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd945-112">Ограничения политики можно добавить к любому действию.</span><span class="sxs-lookup"><span data-stu-id="dd945-112">You can add policy constraints to any activity.</span></span> <span data-ttu-id="dd945-113">Например, можно добавить ограничение политики к действию <xref:System.Activities.Statements.Sequence> или <xref:System.Activities.Statements.Parallel>.</span><span class="sxs-lookup"><span data-stu-id="dd945-113">For example, you can add a policy constraint to a <xref:System.Activities.Statements.Sequence> or <xref:System.Activities.Statements.Parallel> activity.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dd945-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="dd945-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="dd945-115">Откройте файл ExternalActivityValidation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd945-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExternalActivityValidation.sln file.</span></span>  
  
2.  <span data-ttu-id="dd945-116">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="dd945-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="dd945-117">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="dd945-117">To run the solution, press Ctrl+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd945-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dd945-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dd945-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dd945-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd945-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd945-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd945-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dd945-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`