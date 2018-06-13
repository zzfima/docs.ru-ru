---
title: Обработка ошибок в действии блок-схемы с помощью TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: cc7630be868a5bdc1a07e8d935e5dd3269b4ae22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518067"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="b0055-102">Обработка ошибок в действии блок-схемы с помощью TryCatch</span><span class="sxs-lookup"><span data-stu-id="b0055-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>
<span data-ttu-id="b0055-103">В этом образце показано использование действия <xref:System.Activities.Statements.TryCatch> в рамках действия сложного потока управления.</span><span class="sxs-lookup"><span data-stu-id="b0055-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>  
  
 <span data-ttu-id="b0055-104">В этом образце промокод и несколько дочерних элементов передаются как переменные в действие <xref:System.Activities.Statements.Flowchart>, которое вычисляет скидку на основе формулы, которая соответствует промокоду.</span><span class="sxs-lookup"><span data-stu-id="b0055-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="b0055-105">Образец включает императивный код и версии конструктора рабочих процессов образца.</span><span class="sxs-lookup"><span data-stu-id="b0055-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>  
  
 <span data-ttu-id="b0055-106">В следующей таблице представлены переменные для действия `CreateFlowchartWithFaults`.</span><span class="sxs-lookup"><span data-stu-id="b0055-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>  
  
|<span data-ttu-id="b0055-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0055-107">Parameters</span></span>|<span data-ttu-id="b0055-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b0055-108">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b0055-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="b0055-109">promoCode</span></span>|<span data-ttu-id="b0055-110">Промокод.</span><span class="sxs-lookup"><span data-stu-id="b0055-110">The promotion code.</span></span> <span data-ttu-id="b0055-111">Тип данных: String</span><span class="sxs-lookup"><span data-stu-id="b0055-111">Type: String</span></span><br /><br /> <span data-ttu-id="b0055-112">Возможные значения с описанием в скобках.</span><span class="sxs-lookup"><span data-stu-id="b0055-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="b0055-113">-Одно (один)</span><span class="sxs-lookup"><span data-stu-id="b0055-113">-   Single (Single)</span></span><br /><span data-ttu-id="b0055-114">-MNK (женат, детей нет.)</span><span class="sxs-lookup"><span data-stu-id="b0055-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="b0055-115">-MWK (женат, детей.)</span><span class="sxs-lookup"><span data-stu-id="b0055-115">-   MWK (Married with kids.)</span></span>|  
|<span data-ttu-id="b0055-116">numKids</span><span class="sxs-lookup"><span data-stu-id="b0055-116">numKids</span></span>|<span data-ttu-id="b0055-117">Число детей.</span><span class="sxs-lookup"><span data-stu-id="b0055-117">The number of children.</span></span> <span data-ttu-id="b0055-118">Тип: int</span><span class="sxs-lookup"><span data-stu-id="b0055-118">Type: int</span></span>|  
  
 <span data-ttu-id="b0055-119">Действие `CreateFlowchartWithFaults` использует действие <xref:System.Activities.Statements.FlowSwitch%601>, которое производит переключения на аргументе `promoCode` и вычисляет скидку с использованием следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="b0055-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>  
  
|<span data-ttu-id="b0055-120">Значение `promoCode`</span><span class="sxs-lookup"><span data-stu-id="b0055-120">Value of `promoCode`</span></span>|<span data-ttu-id="b0055-121">Скидка (%)</span><span class="sxs-lookup"><span data-stu-id="b0055-121">Discount (%)</span></span>|  
|--------------------------|--------------------|  
|<span data-ttu-id="b0055-122">Single</span><span class="sxs-lookup"><span data-stu-id="b0055-122">Single</span></span>|<span data-ttu-id="b0055-123">10</span><span class="sxs-lookup"><span data-stu-id="b0055-123">10</span></span>|  
|<span data-ttu-id="b0055-124">MNK</span><span class="sxs-lookup"><span data-stu-id="b0055-124">MNK</span></span>|<span data-ttu-id="b0055-125">15</span><span class="sxs-lookup"><span data-stu-id="b0055-125">15</span></span>|  
|<span data-ttu-id="b0055-126">MWK</span><span class="sxs-lookup"><span data-stu-id="b0055-126">MWK</span></span>|<span data-ttu-id="b0055-127">15 + (1 – 1 /`numberOfKids`)\*10 **Примечание:** потенциально может вызвать это вычисление <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="b0055-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="b0055-128">Поэтому вычисление скидки упаковано в действие <xref:System.Activities.Statements.TryCatch>, которое кэширует исключение <xref:System.DivideByZeroException> и устанавливает скидку в нуль.</span><span class="sxs-lookup"><span data-stu-id="b0055-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b0055-129">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b0055-129">To use this sample</span></span>  
  
1.  <span data-ttu-id="b0055-130">Откройте файл решения FlowchartWithFaultHandling.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0055-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the FlowchartWithFaultHandling.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b0055-131">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b0055-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b0055-132">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="b0055-132">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0055-133">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0055-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b0055-134">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b0055-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b0055-135">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="b0055-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0055-136">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b0055-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a><span data-ttu-id="b0055-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b0055-137">See Also</span></span>  
 [<span data-ttu-id="b0055-138">Рабочие процессы с блок-схемой</span><span class="sxs-lookup"><span data-stu-id="b0055-138">Flowchart Workflows</span></span>](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [<span data-ttu-id="b0055-139">Исключения</span><span class="sxs-lookup"><span data-stu-id="b0055-139">Exceptions</span></span>](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
