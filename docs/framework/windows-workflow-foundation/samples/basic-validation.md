---
title: "Базовая проверка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2712ca923d8608fe9e26dba380476993d35b6a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="basic-validation"></a><span data-ttu-id="69c9a-102">Базовая проверка</span><span class="sxs-lookup"><span data-stu-id="69c9a-102">Basic Validation</span></span>
<span data-ttu-id="69c9a-103">Этот образец демонстрирует действие `CreateProduct`, проверяющее, что аргумент `Cost` меньше аргумента `Price` или равен ему.</span><span class="sxs-lookup"><span data-stu-id="69c9a-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="69c9a-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="69c9a-104">Sample Details</span></span>  
 <span data-ttu-id="69c9a-105">Проверку осуществляют два создателя: создатель действия (создает логику проверки для действия) и создатель рабочего процесса, вызывающий службы проверки для конкретного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="69c9a-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="69c9a-106">В этом сценарии создатель действия желает обеспечить стоимость каждого экземпляра действия, которая меньше цены или равна ей.</span><span class="sxs-lookup"><span data-stu-id="69c9a-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="69c9a-107">Создатель действия (внутри действия) должен:</span><span class="sxs-lookup"><span data-stu-id="69c9a-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="69c9a-108">Создайте ограничение (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="69c9a-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="69c9a-109">Здесь размещается вся логика проверки.</span><span class="sxs-lookup"><span data-stu-id="69c9a-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="69c9a-110">Переопределите `System.Activities.CodeActivity.OnGetConstraints()` и добавьте ограничение (`PriceGreaterThanCost`) в список ограничений <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="69c9a-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="69c9a-111">Создатель рабочего процесса (главная программа) должен:</span><span class="sxs-lookup"><span data-stu-id="69c9a-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="69c9a-112">Создайте рабочий процесс с экземпляром действия для проверки (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="69c9a-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="69c9a-113">Вызывает метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="69c9a-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="69c9a-114">Напечатайте объекты <xref:System.Activities.Validation.ValidationError> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="69c9a-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="69c9a-115">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="69c9a-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="69c9a-116">Откройте образец решения BasicValidation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c9a-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="69c9a-117">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="69c9a-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="69c9a-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="69c9a-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="69c9a-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="69c9a-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="69c9a-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69c9a-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="69c9a-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="69c9a-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`