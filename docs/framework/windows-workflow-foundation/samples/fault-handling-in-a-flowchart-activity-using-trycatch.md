---
title: Обработка ошибок в действии блок-схемы с помощью TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 8e3ca59bc9743300a230877a6fbcbed5468a1589
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710828"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="d44c6-102">Обработка ошибок в действии блок-схемы с помощью TryCatch</span><span class="sxs-lookup"><span data-stu-id="d44c6-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>

<span data-ttu-id="d44c6-103">В этом образце показано использование действия <xref:System.Activities.Statements.TryCatch> в рамках действия сложного потока управления.</span><span class="sxs-lookup"><span data-stu-id="d44c6-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>

<span data-ttu-id="d44c6-104">В этом образце промокод и несколько дочерних элементов передаются как переменные в действие <xref:System.Activities.Statements.Flowchart>, которое вычисляет скидку на основе формулы, которая соответствует промокоду.</span><span class="sxs-lookup"><span data-stu-id="d44c6-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="d44c6-105">Образец включает императивный код и версии конструктора рабочих процессов образца.</span><span class="sxs-lookup"><span data-stu-id="d44c6-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>

<span data-ttu-id="d44c6-106">В следующей таблице представлены переменные для действия `CreateFlowchartWithFaults`.</span><span class="sxs-lookup"><span data-stu-id="d44c6-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>

|<span data-ttu-id="d44c6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d44c6-107">Parameters</span></span>|<span data-ttu-id="d44c6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d44c6-108">Description</span></span>|
|----------------|-----------------|
|<span data-ttu-id="d44c6-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="d44c6-109">promoCode</span></span>|<span data-ttu-id="d44c6-110">Промокод.</span><span class="sxs-lookup"><span data-stu-id="d44c6-110">The promotion code.</span></span> <span data-ttu-id="d44c6-111">Тип данных: String</span><span class="sxs-lookup"><span data-stu-id="d44c6-111">Type: String</span></span><br /><br /> <span data-ttu-id="d44c6-112">Возможные значения с описанием в скобках.</span><span class="sxs-lookup"><span data-stu-id="d44c6-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="d44c6-113">-Single (одиночная)</span><span class="sxs-lookup"><span data-stu-id="d44c6-113">-   Single (Single)</span></span><br /><span data-ttu-id="d44c6-114">— МНК (в браке нет детей).</span><span class="sxs-lookup"><span data-stu-id="d44c6-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="d44c6-115">— МВК (в браке).</span><span class="sxs-lookup"><span data-stu-id="d44c6-115">-   MWK (Married with kids.)</span></span>|
|<span data-ttu-id="d44c6-116">numKids</span><span class="sxs-lookup"><span data-stu-id="d44c6-116">numKids</span></span>|<span data-ttu-id="d44c6-117">Число детей.</span><span class="sxs-lookup"><span data-stu-id="d44c6-117">The number of children.</span></span> <span data-ttu-id="d44c6-118">Тип: int</span><span class="sxs-lookup"><span data-stu-id="d44c6-118">Type: int</span></span>|

<span data-ttu-id="d44c6-119">Действие `CreateFlowchartWithFaults` использует действие <xref:System.Activities.Statements.FlowSwitch%601>, которое производит переключения на аргументе `promoCode` и вычисляет скидку с использованием следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="d44c6-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>

|<span data-ttu-id="d44c6-120">Значение `promoCode`</span><span class="sxs-lookup"><span data-stu-id="d44c6-120">Value of `promoCode`</span></span>|<span data-ttu-id="d44c6-121">Скидка (%)</span><span class="sxs-lookup"><span data-stu-id="d44c6-121">Discount (%)</span></span>|
|--------------------------|--------------------|
|<span data-ttu-id="d44c6-122">Single</span><span class="sxs-lookup"><span data-stu-id="d44c6-122">Single</span></span>|<span data-ttu-id="d44c6-123">10</span><span class="sxs-lookup"><span data-stu-id="d44c6-123">10</span></span>|
|<span data-ttu-id="d44c6-124">MNK</span><span class="sxs-lookup"><span data-stu-id="d44c6-124">MNK</span></span>|<span data-ttu-id="d44c6-125">15</span><span class="sxs-lookup"><span data-stu-id="d44c6-125">15</span></span>|
|<span data-ttu-id="d44c6-126">MWK</span><span class="sxs-lookup"><span data-stu-id="d44c6-126">MWK</span></span>|<span data-ttu-id="d44c6-127">15 + (1 – 1/`numberOfKids`)\*10 **Примечание.** возможно, это вычисление может вызвать <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="d44c6-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="d44c6-128">Поэтому вычисление скидки упаковано в действие <xref:System.Activities.Statements.TryCatch>, которое кэширует исключение <xref:System.DivideByZeroException> и устанавливает скидку в нуль.</span><span class="sxs-lookup"><span data-stu-id="d44c6-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="d44c6-129">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="d44c6-129">To use this sample</span></span>

1. <span data-ttu-id="d44c6-130">С помощью Visual Studio 2010 откройте файл решения Фловчартвисфаулсандлинг. sln.</span><span class="sxs-lookup"><span data-stu-id="d44c6-130">Using Visual Studio 2010, open the FlowchartWithFaultHandling.sln solution file.</span></span>

2. <span data-ttu-id="d44c6-131">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="d44c6-131">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="d44c6-132">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="d44c6-132">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d44c6-133">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d44c6-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d44c6-134">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d44c6-134">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="d44c6-135">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="d44c6-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d44c6-136">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d44c6-136">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a><span data-ttu-id="d44c6-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="d44c6-137">See also</span></span>

- [<span data-ttu-id="d44c6-138">Рабочие процессы с блок-схемой</span><span class="sxs-lookup"><span data-stu-id="d44c6-138">Flowchart Workflows</span></span>](../flowchart-workflows.md)
- [<span data-ttu-id="d44c6-139">Исключения</span><span class="sxs-lookup"><span data-stu-id="d44c6-139">Exceptions</span></span>](../exceptions.md)
