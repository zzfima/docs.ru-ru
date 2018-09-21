---
title: Базовая проверка
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46539477"
---
# <a name="basic-validation"></a><span data-ttu-id="87086-102">Базовая проверка</span><span class="sxs-lookup"><span data-stu-id="87086-102">Basic Validation</span></span>
<span data-ttu-id="87086-103">Этот образец демонстрирует действие `CreateProduct`, проверяющее, что аргумент `Cost` меньше аргумента `Price` или равен ему.</span><span class="sxs-lookup"><span data-stu-id="87086-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="87086-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="87086-104">Sample Details</span></span>  
 <span data-ttu-id="87086-105">Проверку осуществляют два создателя: создатель действия (создает логику проверки для действия) и создатель рабочего процесса, вызывающий службы проверки для конкретного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="87086-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="87086-106">В этом сценарии создатель действия желает обеспечить стоимость каждого экземпляра действия, которая меньше цены или равна ей.</span><span class="sxs-lookup"><span data-stu-id="87086-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="87086-107">Создатель действия (внутри действия) должен:</span><span class="sxs-lookup"><span data-stu-id="87086-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="87086-108">Создайте ограничение (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="87086-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="87086-109">Здесь размещается вся логика проверки.</span><span class="sxs-lookup"><span data-stu-id="87086-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="87086-110">Переопределите `System.Activities.CodeActivity.OnGetConstraints()` и добавьте ограничение (`PriceGreaterThanCost`) в список ограничений <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="87086-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="87086-111">Создатель рабочего процесса (главная программа) должен:</span><span class="sxs-lookup"><span data-stu-id="87086-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="87086-112">Создайте рабочий процесс с экземпляром действия для проверки (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="87086-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="87086-113">Вызывает метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="87086-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="87086-114">Напечатайте объекты <xref:System.Activities.Validation.ValidationError> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="87086-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="87086-115">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="87086-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="87086-116">Откройте образец решения BasicValidation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87086-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="87086-117">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="87086-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="87086-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="87086-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="87086-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="87086-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="87086-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="87086-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="87086-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="87086-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`