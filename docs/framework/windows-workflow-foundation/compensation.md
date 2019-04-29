---
title: Компенсация
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: af29ba61ff5bede9208f2ab706f5e0ce1ff12274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774287"
---
# <a name="compensation"></a><span data-ttu-id="28222-102">Компенсация</span><span class="sxs-lookup"><span data-stu-id="28222-102">Compensation</span></span>
<span data-ttu-id="28222-103">Компенсация в Windows Workflow Foundation (WF) — это механизм, по которому ранее выполненной работы можно отменить или компенсировать (логикой, определенной приложением) при привели к возникновению ошибки.</span><span class="sxs-lookup"><span data-stu-id="28222-103">Compensation in Windows Workflow Foundation (WF) is the mechanism by which previously completed work can be undone or compensated (following the logic defined by the application) when a subsequent failure occurs.</span></span> <span data-ttu-id="28222-104">В данном разделе описывается применение компенсации в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="28222-104">This section describes how to use compensation in workflows.</span></span>  
  
## <a name="compensation-vs-transactions"></a><span data-ttu-id="28222-105">Компенсация и Транзакции</span><span class="sxs-lookup"><span data-stu-id="28222-105">Compensation vs. Transactions</span></span>  
 <span data-ttu-id="28222-106">Транзакция позволяет объединить несколько операций в одну единицу работы.</span><span class="sxs-lookup"><span data-stu-id="28222-106">A transaction allows you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="28222-107">Использование транзакции дает приложению возможность прерывать (откатывать) все изменения, выполненные в транзакции, если во время выполнения какой-либо части обработки транзакции возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="28222-107">Using a transaction gives your application the ability to abort (roll back) all changes executed from within the transaction if any errors occur during any part of the transaction process.</span></span> <span data-ttu-id="28222-108">Однако использование транзакций может быть неприемлемо, если работа является долговременной.</span><span class="sxs-lookup"><span data-stu-id="28222-108">However, using transactions may not be appropriate if the work is long running.</span></span> <span data-ttu-id="28222-109">Пусть, например, приложение планирования путешествия реализовано как рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="28222-109">For example, a travel planning application is implemented as a workflow.</span></span> <span data-ttu-id="28222-110">Шагами рабочего процесса могут быть заказ авиабилетов, ожидание подтверждения диспетчера и, наконец, оплата билета.</span><span class="sxs-lookup"><span data-stu-id="28222-110">The steps of the workflow may consist of booking a flight, waiting for manager approval, and then paying for the flight.</span></span> <span data-ttu-id="28222-111">Этот процесс может занять несколько дней, и включение шагов заказа и оплаты авиабилетов в одну транзакцию непрактично.</span><span class="sxs-lookup"><span data-stu-id="28222-111">This process could take many days and it is not practical for the steps of booking and paying for the flight to participate in the same transaction.</span></span> <span data-ttu-id="28222-112">Если позднее в процессе произойдет ошибка, в таком сценарии можно воспользоваться компенсацией для отмены шага заказа в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="28222-112">In a scenario such as this, compensation could be used to undo the booking step of the workflow if there is a failure later in the processing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28222-113">В этом разделе описывается компенсация в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="28222-113">This topic covers compensation in workflows.</span></span> <span data-ttu-id="28222-114">Дополнительные сведения о транзакциях в рабочих процессах см. в разделе [транзакций](workflow-transactions.md) и <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="28222-114">For more information about transactions in workflows, see [Transactions](workflow-transactions.md) and <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="28222-115">Дополнительные сведения о транзакциях см. в разделе <xref:System.Transactions?displayProperty=nameWithType> и <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28222-115">For more information about transactions, see <xref:System.Transactions?displayProperty=nameWithType> and <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span></span>  
  
## <a name="using-compensableactivity"></a><span data-ttu-id="28222-116">Использование действия CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="28222-116">Using CompensableActivity</span></span>  
 <span data-ttu-id="28222-117"><xref:System.Activities.Statements.CompensableActivity> - это базовое действие компенсации в [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28222-117"><xref:System.Activities.Statements.CompensableActivity> is the core compensation activity in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="28222-118">Все выполняющие работу действия, для которых может понадобиться выполнить компенсацию, помещаются в элемент <xref:System.Activities.Statements.CompensableActivity.Body%2A> действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28222-118">Any activities that perform work that may need to be compensated are placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="28222-119">В данном примере шаг бронирования при покупке авиабилета размещен в элементе <xref:System.Activities.Statements.CompensableActivity.Body%2A> действия <xref:System.Activities.Statements.CompensableActivity>, а отмена бронирования помещается в обработчик <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="28222-119">In this example, the reservation step of purchasing a flight is placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> and the cancellation of the reservation is placed into the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span></span> <span data-ttu-id="28222-120">Сразу за действием <xref:System.Activities.Statements.CompensableActivity> в рабочем процессе идут два действия, ожидающие одобрения от диспетчера и выполняющие шаг приобретения билета.</span><span class="sxs-lookup"><span data-stu-id="28222-120">Immediately following the <xref:System.Activities.Statements.CompensableActivity> in the workflow are two activities that wait for manager approval and then complete the purchasing step of the flight.</span></span> <span data-ttu-id="28222-121">Если состояние ошибки вызывает отмену рабочего процесса после успешного завершения работы действия <xref:System.Activities.Statements.CompensableActivity>, то действия в обработчике <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> планируются к выполнению, а полет отменяется.</span><span class="sxs-lookup"><span data-stu-id="28222-121">If an error condition causes the workflow to be canceled after the <xref:System.Activities.Statements.CompensableActivity> has successfully completed, then the activities in the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> handler are scheduled and the flight is canceled.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 <span data-ttu-id="28222-122">Далее показан пример рабочего процесса в XAML.</span><span class="sxs-lookup"><span data-stu-id="28222-122">The following example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="28222-123">При вызове рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="28222-123">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="28222-124">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="28222-124">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="28222-125">**ManagerApproval: Полученные утверждения руководителем.** </span><span class="sxs-lookup"><span data-stu-id="28222-125">**ManagerApproval: Manager approval received.** </span></span>  
<span data-ttu-id="28222-126">**PurchaseFlight: Билет приобретен.** </span><span class="sxs-lookup"><span data-stu-id="28222-126">**PurchaseFlight: Ticket is purchased.** </span></span>  
<span data-ttu-id="28222-127">**Рабочий процесс успешно выполнен с состоянием: Закрыто.**</span><span class="sxs-lookup"><span data-stu-id="28222-127">**Workflow completed successfully with status: Closed.**</span></span>    
> [!NOTE]
>  <span data-ttu-id="28222-128">В образцах действий этого раздела, таких как `ReserveFlight`, на консоли отображается их название и назначение для иллюстрации порядка, в котором действия выполняются при возникновении компенсации.</span><span class="sxs-lookup"><span data-stu-id="28222-128">The sample activities in this topic such as `ReserveFlight` display their name and purpose to the console to help illustrate the order in which the activities are executed when compensation occurs.</span></span>  
  
### <a name="default-workflow-compensation"></a><span data-ttu-id="28222-129">Компенсация рабочего процесса по умолчанию</span><span class="sxs-lookup"><span data-stu-id="28222-129">Default Workflow Compensation</span></span>  
 <span data-ttu-id="28222-130">По умолчанию, если рабочий процесс отменяется, то логика компенсации выполняется для всех подлежащих компенсации действий, которые уже успешно выполнены, но еще не были подтверждены или компенсированы.</span><span class="sxs-lookup"><span data-stu-id="28222-130">By default, if the workflow is canceled, the compensation logic is run for any compensable activity that has successfully completely and has not already been confirmed or compensated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28222-131">При <xref:System.Activities.Statements.CompensableActivity> — *подтверждена*, больше не может вызываться компенсации для действия.</span><span class="sxs-lookup"><span data-stu-id="28222-131">When a <xref:System.Activities.Statements.CompensableActivity> is *confirmed*, compensation for the activity can no longer be invoked.</span></span> <span data-ttu-id="28222-132">Процесс подтверждения описывается далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="28222-132">The confirmation process is described later in this section.</span></span>  
  
 <span data-ttu-id="28222-133">В данном примере исключение выдается после бронирования авиабилета, но до шага подтверждения диспетчера.</span><span class="sxs-lookup"><span data-stu-id="28222-133">In this example, an exception is thrown after the flight is reserved but before the manager approval step.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 <span data-ttu-id="28222-134">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="28222-134">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:SimulatedErrorCondition />  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 [!code-csharp[CFX_CompensationExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#100)]  
  
 <span data-ttu-id="28222-135">Если вызывается рабочий процесс, исключение смоделированного условия ошибки обрабатывается ведущим приложением в <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, рабочий процесс отменяется, и вызывается логика компенсации.</span><span class="sxs-lookup"><span data-stu-id="28222-135">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the compensation logic is invoked.</span></span>  
  
 <span data-ttu-id="28222-136">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="28222-136">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="28222-137">**SimulatedErrorCondition: Вызывает исключение ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="28222-137">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="28222-138">**Необработанное исключение рабочего процесса:** </span><span class="sxs-lookup"><span data-stu-id="28222-138">**Workflow Unhandled Exception:** </span></span>  
<span data-ttu-id="28222-139">**System.ApplicationException: Смоделированное состояние ошибки в рабочем процессе.** </span><span class="sxs-lookup"><span data-stu-id="28222-139">**System.ApplicationException: Simulated error condition in the workflow.** </span></span>  
<span data-ttu-id="28222-140">**CancelFlight: Билет отменен.** </span><span class="sxs-lookup"><span data-stu-id="28222-140">**CancelFlight: Ticket is canceled.** </span></span>  
<span data-ttu-id="28222-141">**Рабочий процесс успешно выполнен с состоянием: Отменено.**</span><span class="sxs-lookup"><span data-stu-id="28222-141">**Workflow completed successfully with status: Canceled.**</span></span>    
### <a name="cancellation-and-compensableactivity"></a><span data-ttu-id="28222-142">Отмена и CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="28222-142">Cancellation and CompensableActivity</span></span>  
 <span data-ttu-id="28222-143">Если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> не завершены, и действие отменено, выполняются действия в обработчике <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="28222-143">If the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled, the activities in the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> are executed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28222-144">Обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> вызывается, только если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> не завершены, и действие отменено.</span><span class="sxs-lookup"><span data-stu-id="28222-144">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is only invoked if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled.</span></span> <span data-ttu-id="28222-145">Обработчик <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> выполняется, только если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> успешно завершены, после чего на действии вызвана компенсация.</span><span class="sxs-lookup"><span data-stu-id="28222-145">The <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> is only executed if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have successfully completed and compensation is subsequently invoked on the activity.</span></span>  
  
 <span data-ttu-id="28222-146">Обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> предоставляет разработчикам рабочего процесса возможность предоставить соответствующую логику отмены.</span><span class="sxs-lookup"><span data-stu-id="28222-146">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gives workflow authors the opportunity to provide any appropriate cancellation logic.</span></span> <span data-ttu-id="28222-147">В следующем примере во время выполнения <xref:System.Activities.Statements.CompensableActivity.Body%2A> создается исключение, а затем вызывается обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="28222-147">In the following example, an exception is thrown during the execution of the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, and then the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is invoked.</span></span>  
  
```csharp  
Activity wf = new Sequence()  
{  
    Activities =  
    {  
        new CompensableActivity  
        {  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new ChargeCreditCard(),  
                    new SimulatedErrorCondition(),  
                    new ReserveFlight()  
                }  
            },  
            CompensationHandler = new CancelFlight(),  
            CancellationHandler = new CancelCreditCard()  
        },  
        new ManagerApproval(),  
        new PurchaseFlight()  
    }  
};  
```  
  
 <span data-ttu-id="28222-148">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="28222-148">This example is the workflow in XAML</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <Sequence>  
      <c:ChargeCreditCard />  
      <c:SimulatedErrorCondition />  
      <c:ReserveFlight />  
    </Sequence>  
    <CompensableActivity.CancellationHandler>  
      <c:CancelCreditCard />  
    </CompensableActivity.CancellationHandler>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="28222-149">Если вызывается рабочий процесс, исключение смоделированного условия ошибки обрабатывается ведущим приложением в <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, рабочий процесс отменяется, и вызывается логика отмены объекта <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28222-149">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the cancellation logic of the <xref:System.Activities.Statements.CompensableActivity> is invoked.</span></span> <span data-ttu-id="28222-150">В этом примере логика компенсации и логика отмены имеют различные задачи.</span><span class="sxs-lookup"><span data-stu-id="28222-150">In this example, the compensation logic and the cancellation logic have different goals.</span></span> <span data-ttu-id="28222-151">Успешное завершение <xref:System.Activities.Statements.CompensableActivity.Body%2A> означает, что с кредитной карты были списаны средства, а авиабилет заказан, поэтому компенсация должна отменить оба шага.</span><span class="sxs-lookup"><span data-stu-id="28222-151">If the <xref:System.Activities.Statements.CompensableActivity.Body%2A> completed successfully, then this means the credit card was charged and the flight booked, so the compensation should undo both steps.</span></span> <span data-ttu-id="28222-152">(В этом примере при отмене полета автоматически отменяются обязательства по кредитной карте.) Однако в случае отмены <xref:System.Activities.Statements.CompensableActivity> это означает, что <xref:System.Activities.Statements.CompensableActivity.Body%2A> не была завершена, поэтому логика <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> должна иметь возможность определить, как лучше всего обработать отмену.</span><span class="sxs-lookup"><span data-stu-id="28222-152">(In this example, canceling the flight automatically cancels the credit card charges.) However, if the <xref:System.Activities.Statements.CompensableActivity> is canceled, this means the <xref:System.Activities.Statements.CompensableActivity.Body%2A> did not complete and so the logic of the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> needs to be able to determine how to best handle the cancellation.</span></span> <span data-ttu-id="28222-153">В этом примере <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> отменяет начисление обязательства на кредитную карту, но, поскольку `ReserveFlight` было последним действием в <xref:System.Activities.Statements.CompensableActivity.Body%2A>, попытка отмены авиабилета не выполняется.</span><span class="sxs-lookup"><span data-stu-id="28222-153">In this example, the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancels the credit card charge, but since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, it does not attempt to cancel the flight.</span></span> <span data-ttu-id="28222-154">Поскольку `ReserveFlight` было последним действием в <xref:System.Activities.Statements.CompensableActivity.Body%2A>, если оно успешно завершилось, то <xref:System.Activities.Statements.CompensableActivity.Body%2A> также завершилась и отмена невозможна.</span><span class="sxs-lookup"><span data-stu-id="28222-154">Since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, if it had successfully completed then the <xref:System.Activities.Statements.CompensableActivity.Body%2A> would have completed and no cancellation would be possible.</span></span>  
  
 <span data-ttu-id="28222-155">**Chargecreditcard: начисление обязательства На кредитную карту за авиабилет.**</span><span class="sxs-lookup"><span data-stu-id="28222-155">**ChargeCreditCard: Charge credit card for flight.**</span></span>  
<span data-ttu-id="28222-156">**SimulatedErrorCondition: Вызывает исключение ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="28222-156">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="28222-157">**Необработанное исключение рабочего процесса:** </span><span class="sxs-lookup"><span data-stu-id="28222-157">**Workflow Unhandled Exception:** </span></span>  
<span data-ttu-id="28222-158">**System.ApplicationException: Смоделированное состояние ошибки в рабочем процессе.** </span><span class="sxs-lookup"><span data-stu-id="28222-158">**System.ApplicationException: Simulated error condition in the workflow.** </span></span>  
<span data-ttu-id="28222-159">**CancelCreditCard: Отмените кредитной карте.** </span><span class="sxs-lookup"><span data-stu-id="28222-159">**CancelCreditCard: Cancel credit card charges.** </span></span>  
<span data-ttu-id="28222-160">**Рабочий процесс успешно выполнен с состоянием: Отменено.**</span><span class="sxs-lookup"><span data-stu-id="28222-160">**Workflow completed successfully with status: Canceled.**</span></span>  <span data-ttu-id="28222-161">Дополнительные сведения об отмене см. в разделе [отмены](modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="28222-161">For more information about cancellation, see [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a><span data-ttu-id="28222-162">Явная компенсация с использованием действия компенсации</span><span class="sxs-lookup"><span data-stu-id="28222-162">Explicit Compensation Using the Compensate Activity</span></span>  
 <span data-ttu-id="28222-163">В предыдущем разделе была описана неявная компенсация.</span><span class="sxs-lookup"><span data-stu-id="28222-163">In the previous section, implicit compensation was covered.</span></span> <span data-ttu-id="28222-164">Неявная компенсация может использоваться в простых сценариях, но если требуется более явный контроль над планированием обработки компенсации, можно использовать действие <xref:System.Activities.Statements.Compensate>.</span><span class="sxs-lookup"><span data-stu-id="28222-164">Implicit compensation can be appropriate for simple scenarios, but if more explicit control is required over the scheduling of compensation handling then the <xref:System.Activities.Statements.Compensate> activity can be used.</span></span> <span data-ttu-id="28222-165">Для инициации процесса компенсации с применением действия <xref:System.Activities.Statements.Compensate> используется маркер <xref:System.Activities.Statements.CompensationToken> действия <xref:System.Activities.Statements.CompensableActivity>, для которого необходимо провести компенсацию.</span><span class="sxs-lookup"><span data-stu-id="28222-165">To initiate the compensation process with the <xref:System.Activities.Statements.Compensate> activity, the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> for which compensation is desired is used.</span></span> <span data-ttu-id="28222-166">Действие <xref:System.Activities.Statements.Compensate> может использоваться для запуска компенсации для любого выполненного действия <xref:System.Activities.Statements.CompensableActivity>, которое не было подтверждено или компенсировано.</span><span class="sxs-lookup"><span data-stu-id="28222-166">The <xref:System.Activities.Statements.Compensate> activity can be used to initiate compensation on any completed <xref:System.Activities.Statements.CompensableActivity> that has not been confirmed or compensated.</span></span> <span data-ttu-id="28222-167">Например, действие <xref:System.Activities.Statements.Compensate> может использоваться в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A> действия <xref:System.Activities.Statements.TryCatch> или в любой момент после завершения действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28222-167">For example, a <xref:System.Activities.Statements.Compensate> activity could be used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity, or any time after the <xref:System.Activities.Statements.CompensableActivity> has completed.</span></span> <span data-ttu-id="28222-168">В данном примере действие <xref:System.Activities.Statements.Compensate> используется в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A> действия <xref:System.Activities.Statements.TryCatch> для обращения действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28222-168">In this example, the <xref:System.Activities.Statements.Compensate> activity is used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity to reverse the action of the <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 <span data-ttu-id="28222-169">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="28222-169">This example is the workflow in XAML.</span></span>  
  
```xaml  
<TryCatch  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:s="clr-namespace:System;assembly=mscorlib"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <TryCatch.Variables>  
    <Variable  
       x:TypeArguments="CompensationToken"  
       x:Name="__ReferenceID0"  
       Name="token1" />  
  </TryCatch.Variables>  
  <TryCatch.Try>  
    <Sequence>  
      <CompensableActivity>  
        <CompensableActivity.Result>  
          <OutArgument  
             x:TypeArguments="CompensationToken">  
            <VariableReference  
               x:TypeArguments="CompensationToken"  
               Variable="{x:Reference __ReferenceID0}">  
              <VariableReference.Result>  
                <OutArgument  
                   x:TypeArguments="Location(CompensationToken)" />  
              </VariableReference.Result>  
            </VariableReference>  
          </OutArgument>  
        </CompensableActivity.Result>  
        <CompensableActivity.CompensationHandler>  
          <c:CancelFlight />  
        </CompensableActivity.CompensationHandler>  
        <CompensableActivity.ConfirmationHandler>  
          <c:ConfirmFlight />  
        </CompensableActivity.ConfirmationHandler>  
        <c:ReserveFlight />  
      </CompensableActivity>  
      <c:SimulatedErrorCondition />  
      <c:ManagerApproval />  
      <c:PurchaseFlight />  
    </Sequence>  
  </TryCatch.Try>  
  <TryCatch.Catches>  
    <Catch  
       x:TypeArguments="s:ApplicationException">  
      <ActivityAction  
         x:TypeArguments="s:ApplicationException">  
        <Compensate>  
          <Compensate.Target>  
            <InArgument  
               x:TypeArguments="CompensationToken">  
              <VariableValue  
                 x:TypeArguments="CompensationToken"  
                 Variable="{x:Reference __ReferenceID0}">  
                <VariableValue.Result>  
                  <OutArgument  
                     x:TypeArguments="CompensationToken" />  
                </VariableValue.Result>  
              </VariableValue>  
            </InArgument>  
          </Compensate.Target>  
        </Compensate>  
      </ActivityAction>  
    </Catch>  
  </TryCatch.Catches>  
</TryCatch>  
```  
  
 <span data-ttu-id="28222-170">При вызове рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="28222-170">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="28222-171">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="28222-171">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="28222-172">**SimulatedErrorCondition: Вызывает исключение ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="28222-172">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="28222-173">**CancelFlight: Билет отменен.** </span><span class="sxs-lookup"><span data-stu-id="28222-173">**CancelFlight: Ticket is canceled.** </span></span>  
<span data-ttu-id="28222-174">**Рабочий процесс успешно выполнен с состоянием: Закрыто.**</span><span class="sxs-lookup"><span data-stu-id="28222-174">**Workflow completed successfully with status: Closed.**</span></span>    
### <a name="confirming-compensation"></a><span data-ttu-id="28222-175">Подтверждение компенсации</span><span class="sxs-lookup"><span data-stu-id="28222-175">Confirming Compensation</span></span>  
 <span data-ttu-id="28222-176">По умолчанию подлежащие компенсации действия могут быть компенсированы в любой момент после их завершения.</span><span class="sxs-lookup"><span data-stu-id="28222-176">By default, compensable activities can be compensated any time after they have completed.</span></span> <span data-ttu-id="28222-177">Но в некоторых ситуациях это может быть невозможно.</span><span class="sxs-lookup"><span data-stu-id="28222-177">In some scenarios this may not be appropriate.</span></span> <span data-ttu-id="28222-178">В предыдущем примере компенсацией для бронирования авиабилета служит отмена бронирования.</span><span class="sxs-lookup"><span data-stu-id="28222-178">In the previous example the compensation to reserving the ticket was to cancel the reservation.</span></span> <span data-ttu-id="28222-179">Однако после выполнения перелета такой шаг компенсации уже недопустим.</span><span class="sxs-lookup"><span data-stu-id="28222-179">However, after the flight has been completed this compensation step is no longer valid.</span></span> <span data-ttu-id="28222-180">Подтверждение подлежащего компенсации действия вызывает действие, заданное обработчиком <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="28222-180">Confirming the compensable activity invokes the activity specified by the <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span></span> <span data-ttu-id="28222-181">Это может использоваться, например, для освобождения любых ресурсов, которые требуются при выполнении компенсации.</span><span class="sxs-lookup"><span data-stu-id="28222-181">One possible use for this is to allow any resources that are necessary to perform the compensation to be released.</span></span> <span data-ttu-id="28222-182">После подтверждения действия, которое могло быть компенсировано, его компенсация становится невозможной, и при попытке такой компенсации возникнет исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="28222-182">After a compensable activity is confirmed it is not possible for it to be compensated, and if this is attempted an <xref:System.InvalidOperationException> exception is thrown.</span></span> <span data-ttu-id="28222-183">Если рабочий процесс завершается успешно, все неподтвержденные и некомпенсированные действия, завершенные успешно, подтверждаются в порядке, обратном порядку их завершения.</span><span class="sxs-lookup"><span data-stu-id="28222-183">When a workflow completes successfully, all non-confirmed and non-compensated compensable activities that completed successfully are confirmed in reverse order of completion.</span></span> <span data-ttu-id="28222-184">В данном примере авиабилет бронируется, приобретается и завершается, после чего выполняется подтверждение действия, подлежащего компенсации.</span><span class="sxs-lookup"><span data-stu-id="28222-184">In this example the flight is reserved, purchased, and completed, and then the compensable activity is confirmed.</span></span> <span data-ttu-id="28222-185">Для подтверждения действия <xref:System.Activities.Statements.CompensableActivity> следует использовать действие <xref:System.Activities.Statements.Confirm> и задать маркер <xref:System.Activities.Statements.CompensationToken> действия <xref:System.Activities.Statements.CompensableActivity>, подлежащего подтверждению.</span><span class="sxs-lookup"><span data-stu-id="28222-185">To confirm a <xref:System.Activities.Statements.CompensableActivity>, use the <xref:System.Activities.Statements.Confirm> activity and specify the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> to confirm.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 <span data-ttu-id="28222-186">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="28222-186">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <x:Reference>__ReferenceID0</x:Reference>  
  </Sequence.Variables>  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken">  
        <VariableReference  
           x:TypeArguments="CompensationToken">  
          <VariableReference.Result>  
            <OutArgument  
               x:TypeArguments="Location(CompensationToken)" />  
          </VariableReference.Result>  
          <VariableReference.Variable>  
            <Variable  
               x:TypeArguments="CompensationToken"  
               x:Name="__ReferenceID0"  
               Name="token1" />  
          </VariableReference.Variable>  
        </VariableReference>  
      </OutArgument>  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <CompensableActivity.ConfirmationHandler>  
      <c:ConfirmFlight />  
    </CompensableActivity.ConfirmationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
  <c:TakeFlight />  
  <Confirm>  
    <Confirm.Target>  
      <InArgument  
         x:TypeArguments="CompensationToken">  
        <VariableValue  
           x:TypeArguments="CompensationToken"  
           Variable="{x:Reference __ReferenceID0}">  
          <VariableValue.Result>  
            <OutArgument  
               x:TypeArguments="CompensationToken" />  
          </VariableValue.Result>  
        </VariableValue>  
      </InArgument>  
    </Confirm.Target>  
  </Confirm>  
</Sequence>  
```  
  
<span data-ttu-id="28222-187">При вызове рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="28222-187">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
<span data-ttu-id="28222-188">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="28222-188">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="28222-189">**ManagerApproval: Полученные утверждения руководителем.** </span><span class="sxs-lookup"><span data-stu-id="28222-189">**ManagerApproval: Manager approval received.** </span></span>  
<span data-ttu-id="28222-190">**PurchaseFlight: Билет приобретен.** </span><span class="sxs-lookup"><span data-stu-id="28222-190">**PurchaseFlight: Ticket is purchased.** </span></span>  
<span data-ttu-id="28222-191">**TakeFlight: Перелет выполнен.** </span><span class="sxs-lookup"><span data-stu-id="28222-191">**TakeFlight: Flight is completed.** </span></span>  
<span data-ttu-id="28222-192">**ConfirmFlight: Flight не будет принято, компенсация возможных.** </span><span class="sxs-lookup"><span data-stu-id="28222-192">**ConfirmFlight: Flight has been taken, no compensation possible.** </span></span>  
<span data-ttu-id="28222-193">**Рабочий процесс успешно выполнен с состоянием: Закрыто.**</span><span class="sxs-lookup"><span data-stu-id="28222-193">**Workflow completed successfully with status: Closed.**</span></span>   

## <a name="nesting-compensation-activities"></a><span data-ttu-id="28222-194">Вложенные действия компенсации</span><span class="sxs-lookup"><span data-stu-id="28222-194">Nesting Compensation Activities</span></span>  

<span data-ttu-id="28222-195">Действие <xref:System.Activities.Statements.CompensableActivity> может быть помещено в раздел <xref:System.Activities.Statements.CompensableActivity.Body%2A> другого действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28222-195">A <xref:System.Activities.Statements.CompensableActivity> can be placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> section of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="28222-196">Объект <xref:System.Activities.Statements.CompensableActivity> не может быть помещен в обработчик другого <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="28222-196">A <xref:System.Activities.Statements.CompensableActivity> may not be placed into a handler of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="28222-197">Родительское действие <xref:System.Activities.Statements.CompensableActivity> обязано убедиться в том, что при отмене, подтверждении или компенсации все дочерние действия, подлежащие компенсации, которые успешно завершились и еще не подтверждены и не компенсированы, должны быть подтверждены или компенсированы перед тем, как родительское действие завершит отмену, подтверждение или компенсацию.</span><span class="sxs-lookup"><span data-stu-id="28222-197">It is the responsibility of a parent <xref:System.Activities.Statements.CompensableActivity> to ensure that when it is canceled, confirmed, or compensated, all child compensable activities that have completed successfully and have not already been confirmed or compensated must be confirmed or compensated before the parent completes cancellation, confirmation, or compensation.</span></span> <span data-ttu-id="28222-198">Если это не моделируется явным образом, родительское действие <xref:System.Activities.Statements.CompensableActivity> неявно компенсирует дочерние действия, подлежащие компенсации, если получит сигнал отмены или компенсации.</span><span class="sxs-lookup"><span data-stu-id="28222-198">If this is not modeled explicitly the parent <xref:System.Activities.Statements.CompensableActivity> will implicitly compensate child compensable activities if the parent received the cancel or compensate signal.</span></span> <span data-ttu-id="28222-199">Если родитель получил сигнал подтверждения, родитель неявно подтвердит дочерние действия, подлежащие компенсации.</span><span class="sxs-lookup"><span data-stu-id="28222-199">If the parent received the confirm signal the parent will implicitly confirm child compensable activities.</span></span> <span data-ttu-id="28222-200">Если логика обработки отмены, подтверждения или компенсации явным образом моделируется в обработчике родительского <xref:System.Activities.Statements.CompensableActivity>, то любое явно не обработанное дочернее действие будет неявно подтверждено.</span><span class="sxs-lookup"><span data-stu-id="28222-200">If the logic to handle cancellation, confirmation, or compensation is explicitly modeled in the handler of the parent <xref:System.Activities.Statements.CompensableActivity>, any child not explicitly handled will be implicitly confirmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28222-201">См. также</span><span class="sxs-lookup"><span data-stu-id="28222-201">See also</span></span>

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
