---
title: Дополнительная политика
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: becdc28affd877239474d6f0f007a480297bccb8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672844"
---
# <a name="advanced-policy"></a><span data-ttu-id="20a08-102">Дополнительная политика</span><span class="sxs-lookup"><span data-stu-id="20a08-102">Advanced Policy</span></span>
<span data-ttu-id="20a08-103">Данный образец выступает как дополнение образца простой политики.</span><span class="sxs-lookup"><span data-stu-id="20a08-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="20a08-104">К правилам для скидок на жилье и коммерческих скидок, описанных в примере простой политики, добавлены несколько новых правил.</span><span class="sxs-lookup"><span data-stu-id="20a08-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="20a08-105">Добавлено правило высокой стоимости, которое предоставляет большую скидку на заказы высокой стоимости.</span><span class="sxs-lookup"><span data-stu-id="20a08-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="20a08-106">Это правило имеет более низкий приоритет, чем предыдущие два правила, чтобы повторно записывать поля скидки и быть приоритетными по отношению к правилам для скидок на жилье и коммерческих скидок.</span><span class="sxs-lookup"><span data-stu-id="20a08-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="20a08-107">Также добавлено правило расчета общей суммы, которое выполняет вычисление общей суммы в зависимости от уровня скидки.</span><span class="sxs-lookup"><span data-stu-id="20a08-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="20a08-108">Он демонстрирует создание ссылки на метод, определенный для действия рабочего процесса, а также использование остальных действий.</span><span class="sxs-lookup"><span data-stu-id="20a08-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="20a08-109">Данное правило также демонстрирует поведение последовательного соединения, поскольку его вычисление будет выполняться каждый раз при изменении полей скидки.</span><span class="sxs-lookup"><span data-stu-id="20a08-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="20a08-110">Кроме того, показано назначение для метода "CalculateTotal" атрибута "RuleWriteAttribute".</span><span class="sxs-lookup"><span data-stu-id="20a08-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="20a08-111">По этим причинам для связанных правил (ErrorTotalRule) при каждом выполнении метода выполняется повторное вычисление.</span><span class="sxs-lookup"><span data-stu-id="20a08-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="20a08-112">Последнее добавленное правило отвечает за обнаружение ошибок (в данном случае «Общая сумма меньше 0»).</span><span class="sxs-lookup"><span data-stu-id="20a08-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="20a08-113">В этом случае выполнение политики приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="20a08-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="20a08-114">И наконец, вызовы метода `Console.Writeline` добавлены как действия для каждого правила, которые помогают сделать выполнение правила более видимым, одновременно демонстрируя возможность доступа к статическим методам для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="20a08-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="20a08-115">Также можно использовать отслеживание, чтобы повысить видимость выполняемых правил.</span><span class="sxs-lookup"><span data-stu-id="20a08-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="20a08-116">В данном образце используются приведенные ниже правила.</span><span class="sxs-lookup"><span data-stu-id="20a08-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="20a08-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="20a08-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="20a08-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="20a08-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="20a08-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="20a08-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="20a08-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="20a08-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="20a08-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="20a08-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="20a08-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="20a08-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="20a08-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="20a08-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="20a08-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="20a08-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="20a08-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="20a08-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="20a08-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="20a08-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="20a08-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="20a08-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="20a08-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="20a08-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="20a08-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="20a08-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="20a08-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="20a08-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="20a08-131">Если общее \< 0</span><span class="sxs-lookup"><span data-stu-id="20a08-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="20a08-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="20a08-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="20a08-133">Вычисление и выполнение правила также можно просмотреть посредством трассировки и отслеживания.</span><span class="sxs-lookup"><span data-stu-id="20a08-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="20a08-134">Сборка образца</span><span class="sxs-lookup"><span data-stu-id="20a08-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="20a08-135">Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20a08-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="20a08-136">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="20a08-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="20a08-137">Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="20a08-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="20a08-138">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="20a08-138">To run the sample</span></span>  
  
-   <span data-ttu-id="20a08-139">В окне командной строки пакета SDK запустите файл с расширением EXE в папке «AdvancedPolicy\bin\debug» (или в папке «AdvancedPolicy\bin» для образца в Visual Basic), вложенной в главную папку образца.</span><span class="sxs-lookup"><span data-stu-id="20a08-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20a08-140">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="20a08-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="20a08-141">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="20a08-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20a08-142">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="20a08-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20a08-143">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="20a08-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="20a08-144">См. также</span><span class="sxs-lookup"><span data-stu-id="20a08-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="20a08-145">Простая политика</span><span class="sxs-lookup"><span data-stu-id="20a08-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
