---
title: "Типы ограничений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d42be018b6a92237b5914c180d329138fb95e7dc
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="constraint-types"></a><span data-ttu-id="0fe76-102">Типы ограничений</span><span class="sxs-lookup"><span data-stu-id="0fe76-102">Constraint Types</span></span>
<span data-ttu-id="0fe76-103">Этот образец демонстрирует два способа применения ограничений к рабочему процессу, один из которых применяется изнутри действия (сборка), а второй - снаружи действия (политика).</span><span class="sxs-lookup"><span data-stu-id="0fe76-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="0fe76-104">В этом сценарии создатель действия (представитель сторонней компании-разработчика программного обеспечения) желает проверить соотношение между двумя аргументами.</span><span class="sxs-lookup"><span data-stu-id="0fe76-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="0fe76-105">В этом случае стоимость не должна превышать цену.</span><span class="sxs-lookup"><span data-stu-id="0fe76-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="0fe76-106">Это является общим проверочным ограничением для сборки.</span><span class="sxs-lookup"><span data-stu-id="0fe76-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="0fe76-107">Затем владелец магазина желает добавить к этому общему действию ряд других проверок.</span><span class="sxs-lookup"><span data-stu-id="0fe76-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="0fe76-108">Допустим, он желает, чтобы большая часть его продуктов имела стоимость 9,99 долларов или менее.</span><span class="sxs-lookup"><span data-stu-id="0fe76-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="0fe76-109">Для этого он использует ограничение политики, являющееся надстройкой над действием `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="0fe76-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="0fe76-110">В данном образце:</span><span class="sxs-lookup"><span data-stu-id="0fe76-110">In the sample:</span></span>  
  
 <span data-ttu-id="0fe76-111">Создатель действия (сборка) должен:</span><span class="sxs-lookup"><span data-stu-id="0fe76-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="0fe76-112">Создайте ограничение (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="0fe76-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="0fe76-113">Здесь размещается вся логика проверки.</span><span class="sxs-lookup"><span data-stu-id="0fe76-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="0fe76-114">Переопределите `System.Activities.CodeActivity.OnGetConstraints()` и добавьте ограничение (`PriceGreaterThanCost`) в список ограничений <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="0fe76-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="0fe76-115">Создатель рабочего процесса (политика) должен:</span><span class="sxs-lookup"><span data-stu-id="0fe76-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="0fe76-116">Создайте рабочий процесс с экземпляром действия для проверки (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="0fe76-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="0fe76-117">Создайте ограничение (`MaxPrice`).</span><span class="sxs-lookup"><span data-stu-id="0fe76-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="0fe76-118">Создать экземпляр <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) и добавить ограничение (`MaxPrice`) к коллекции `AdditionalConstraints`.</span><span class="sxs-lookup"><span data-stu-id="0fe76-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="0fe76-119">В этом случае создатель рабочего процесса может добавить ограничения политики к любому действию, например, к последовательному или параллельному.</span><span class="sxs-lookup"><span data-stu-id="0fe76-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="0fe76-120">Вызвать метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="0fe76-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="0fe76-121">Напечатайте объекты <xref:System.Activities.Validation.ValidationError> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="0fe76-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0fe76-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="0fe76-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0fe76-123">Откройте образец решения ConstraintTypes.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fe76-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0fe76-124">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="0fe76-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0fe76-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0fe76-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0fe76-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0fe76-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0fe76-127">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fe76-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0fe76-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fe76-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`