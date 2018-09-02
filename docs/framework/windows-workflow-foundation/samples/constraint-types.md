---
title: Типы ограничений
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 202a2c7b3a3fc400552e42c8606457964af66af2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401536"
---
# <a name="constraint-types"></a><span data-ttu-id="7ca83-102">Типы ограничений</span><span class="sxs-lookup"><span data-stu-id="7ca83-102">Constraint Types</span></span>
<span data-ttu-id="7ca83-103">Этот образец демонстрирует два способа применения ограничений к рабочему процессу, один из которых применяется изнутри действия (сборка), а второй - снаружи действия (политика).</span><span class="sxs-lookup"><span data-stu-id="7ca83-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="7ca83-104">В этом сценарии создатель действия (представитель сторонней компании-разработчика программного обеспечения) желает проверить соотношение между двумя аргументами.</span><span class="sxs-lookup"><span data-stu-id="7ca83-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="7ca83-105">В этом случае стоимость не должна превышать цену.</span><span class="sxs-lookup"><span data-stu-id="7ca83-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="7ca83-106">Это является общим проверочным ограничением для сборки.</span><span class="sxs-lookup"><span data-stu-id="7ca83-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="7ca83-107">Затем владелец магазина желает добавить к этому общему действию ряд других проверок.</span><span class="sxs-lookup"><span data-stu-id="7ca83-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="7ca83-108">Допустим, он желает, чтобы большая часть его продуктов имела стоимость 9,99 долларов или менее.</span><span class="sxs-lookup"><span data-stu-id="7ca83-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="7ca83-109">Для этого он использует ограничение политики, являющееся надстройкой над действием `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="7ca83-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="7ca83-110">В данном образце:</span><span class="sxs-lookup"><span data-stu-id="7ca83-110">In the sample:</span></span>  
  
 <span data-ttu-id="7ca83-111">Создатель действия (сборка) должен:</span><span class="sxs-lookup"><span data-stu-id="7ca83-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="7ca83-112">Создайте ограничение (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="7ca83-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="7ca83-113">Здесь размещается вся логика проверки.</span><span class="sxs-lookup"><span data-stu-id="7ca83-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="7ca83-114">Переопределите `System.Activities.CodeActivity.OnGetConstraints()` и добавьте ограничение (`PriceGreaterThanCost`) в список ограничений <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="7ca83-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="7ca83-115">Создатель рабочего процесса (политика) должен:</span><span class="sxs-lookup"><span data-stu-id="7ca83-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="7ca83-116">Создайте рабочий процесс с экземпляром действия для проверки (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="7ca83-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="7ca83-117">Создайте ограничение (`MaxPrice`).</span><span class="sxs-lookup"><span data-stu-id="7ca83-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="7ca83-118">Создать экземпляр <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) и добавить ограничение (`MaxPrice`) к коллекции `AdditionalConstraints`.</span><span class="sxs-lookup"><span data-stu-id="7ca83-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="7ca83-119">В этом случае создатель рабочего процесса может добавить ограничения политики к любому действию, например, к последовательному или параллельному.</span><span class="sxs-lookup"><span data-stu-id="7ca83-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="7ca83-120">Вызвать метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="7ca83-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="7ca83-121">Напечатайте объекты <xref:System.Activities.Validation.ValidationError> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="7ca83-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7ca83-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="7ca83-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7ca83-123">Откройте образец решения ConstraintTypes.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ca83-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ca83-124">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="7ca83-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7ca83-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7ca83-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7ca83-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7ca83-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7ca83-127">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="7ca83-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7ca83-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7ca83-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`