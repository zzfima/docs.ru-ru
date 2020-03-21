---
title: Компенсация
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: 75c5ed2f5e5c3a93834632ce499a2c8195fbc6bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183004"
---
# <a name="compensation"></a><span data-ttu-id="cec3e-102">Компенсация</span><span class="sxs-lookup"><span data-stu-id="cec3e-102">Compensation</span></span>
<span data-ttu-id="cec3e-103">Компенсация в Фонде рабочего процесса Windows (WF) — это механизм, с помощью которого ранее выполненная работа может быть отменена или компенсирована (в соответствии с логикой, определенной приложением), когда происходит последующий сбой.</span><span class="sxs-lookup"><span data-stu-id="cec3e-103">Compensation in Windows Workflow Foundation (WF) is the mechanism by which previously completed work can be undone or compensated (following the logic defined by the application) when a subsequent failure occurs.</span></span> <span data-ttu-id="cec3e-104">В данном разделе описывается применение компенсации в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="cec3e-104">This section describes how to use compensation in workflows.</span></span>  
  
## <a name="compensation-vs-transactions"></a><span data-ttu-id="cec3e-105">Сравнение компенсации и транзакций</span><span class="sxs-lookup"><span data-stu-id="cec3e-105">Compensation vs. Transactions</span></span>  
 <span data-ttu-id="cec3e-106">Транзакция позволяет объединить несколько операций в одну единицу работы.</span><span class="sxs-lookup"><span data-stu-id="cec3e-106">A transaction allows you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="cec3e-107">Использование транзакции дает приложению возможность прерывать (откатывать) все изменения, выполненные в транзакции, если во время выполнения какой-либо части обработки транзакции возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="cec3e-107">Using a transaction gives your application the ability to abort (roll back) all changes executed from within the transaction if any errors occur during any part of the transaction process.</span></span> <span data-ttu-id="cec3e-108">Однако использование транзакций может быть неприемлемо, если работа является долговременной.</span><span class="sxs-lookup"><span data-stu-id="cec3e-108">However, using transactions may not be appropriate if the work is long running.</span></span> <span data-ttu-id="cec3e-109">Пусть, например, приложение планирования путешествия реализовано как рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="cec3e-109">For example, a travel planning application is implemented as a workflow.</span></span> <span data-ttu-id="cec3e-110">Шагами рабочего процесса могут быть заказ авиабилетов, ожидание подтверждения диспетчера и, наконец, оплата билета.</span><span class="sxs-lookup"><span data-stu-id="cec3e-110">The steps of the workflow may consist of booking a flight, waiting for manager approval, and then paying for the flight.</span></span> <span data-ttu-id="cec3e-111">Этот процесс может занять несколько дней, и включение шагов заказа и оплаты авиабилетов в одну транзакцию непрактично.</span><span class="sxs-lookup"><span data-stu-id="cec3e-111">This process could take many days and it is not practical for the steps of booking and paying for the flight to participate in the same transaction.</span></span> <span data-ttu-id="cec3e-112">Если позднее в процессе произойдет ошибка, в таком сценарии можно воспользоваться компенсацией для отмены шага заказа в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="cec3e-112">In a scenario such as this, compensation could be used to undo the booking step of the workflow if there is a failure later in the processing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cec3e-113">В этом разделе описывается компенсация в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="cec3e-113">This topic covers compensation in workflows.</span></span> <span data-ttu-id="cec3e-114">Для получения дополнительной информации о транзакциях в рабочих процессах см. [Transactions](workflow-transactions.md) <xref:System.Activities.Statements.TransactionScope></span><span class="sxs-lookup"><span data-stu-id="cec3e-114">For more information about transactions in workflows, see [Transactions](workflow-transactions.md) and <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="cec3e-115">Для получения дополнительной информации <xref:System.Transactions.Transaction?displayProperty=nameWithType>о транзакциях, см. <xref:System.Transactions?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cec3e-115">For more information about transactions, see <xref:System.Transactions?displayProperty=nameWithType> and <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span></span>  
  
## <a name="using-compensableactivity"></a><span data-ttu-id="cec3e-116">Использование действия CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="cec3e-116">Using CompensableActivity</span></span>  
 <span data-ttu-id="cec3e-117"><xref:System.Activities.Statements.CompensableActivity> - это базовое действие компенсации в [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec3e-117"><xref:System.Activities.Statements.CompensableActivity> is the core compensation activity in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="cec3e-118">Все выполняющие работу действия, для которых может понадобиться выполнить компенсацию, помещаются в элемент <xref:System.Activities.Statements.CompensableActivity.Body%2A> действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-118">Any activities that perform work that may need to be compensated are placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="cec3e-119">В данном примере шаг бронирования при покупке авиабилета размещен в элементе <xref:System.Activities.Statements.CompensableActivity.Body%2A> действия <xref:System.Activities.Statements.CompensableActivity>, а отмена бронирования помещается в обработчик <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-119">In this example, the reservation step of purchasing a flight is placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> and the cancellation of the reservation is placed into the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span></span> <span data-ttu-id="cec3e-120">Сразу за действием <xref:System.Activities.Statements.CompensableActivity> в рабочем процессе идут два действия, ожидающие одобрения от диспетчера и выполняющие шаг приобретения билета.</span><span class="sxs-lookup"><span data-stu-id="cec3e-120">Immediately following the <xref:System.Activities.Statements.CompensableActivity> in the workflow are two activities that wait for manager approval and then complete the purchasing step of the flight.</span></span> <span data-ttu-id="cec3e-121">Если состояние ошибки вызывает отмену рабочего процесса после успешного завершения работы действия <xref:System.Activities.Statements.CompensableActivity>, то действия в обработчике <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> планируются к выполнению, а полет отменяется.</span><span class="sxs-lookup"><span data-stu-id="cec3e-121">If an error condition causes the workflow to be canceled after the <xref:System.Activities.Statements.CompensableActivity> has successfully completed, then the activities in the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> handler are scheduled and the flight is canceled.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 <span data-ttu-id="cec3e-122">Далее показан пример рабочего процесса в XAML.</span><span class="sxs-lookup"><span data-stu-id="cec3e-122">The following example is the workflow in XAML.</span></span>  
  
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
  
 <span data-ttu-id="cec3e-123">При вызове рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="cec3e-123">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="cec3e-124">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-124">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="cec3e-125">**ManagerApproval: Менеджер одобрение получено.** 
 **PurchaseFlight: Билет приобретается.** 
 **Рабочий процесс успешно завершен со статусом: Закрыто.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-125">**ManagerApproval: Manager approval received.**
**PurchaseFlight: Ticket is purchased.**
**Workflow completed successfully with status: Closed.**</span></span>
> [!NOTE]
> <span data-ttu-id="cec3e-126">В образцах действий этого раздела, таких как `ReserveFlight`, на консоли отображается их название и назначение для иллюстрации порядка, в котором действия выполняются при возникновении компенсации.</span><span class="sxs-lookup"><span data-stu-id="cec3e-126">The sample activities in this topic such as `ReserveFlight` display their name and purpose to the console to help illustrate the order in which the activities are executed when compensation occurs.</span></span>  
  
### <a name="default-workflow-compensation"></a><span data-ttu-id="cec3e-127">Компенсация рабочего процесса по умолчанию</span><span class="sxs-lookup"><span data-stu-id="cec3e-127">Default Workflow Compensation</span></span>  
 <span data-ttu-id="cec3e-128">По умолчанию, если рабочий процесс отменяется, то логика компенсации выполняется для всех подлежащих компенсации действий, которые уже успешно выполнены, но еще не были подтверждены или компенсированы.</span><span class="sxs-lookup"><span data-stu-id="cec3e-128">By default, if the workflow is canceled, the compensation logic is run for any compensable activity that has successfully completely and has not already been confirmed or compensated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cec3e-129">При <xref:System.Activities.Statements.CompensableActivity> *подтверждении,* компенсация за действие больше не может быть вызвана.</span><span class="sxs-lookup"><span data-stu-id="cec3e-129">When a <xref:System.Activities.Statements.CompensableActivity> is *confirmed*, compensation for the activity can no longer be invoked.</span></span> <span data-ttu-id="cec3e-130">Процесс подтверждения описывается далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="cec3e-130">The confirmation process is described later in this section.</span></span>  
  
 <span data-ttu-id="cec3e-131">В данном примере исключение выдается после бронирования авиабилета, но до шага подтверждения диспетчера.</span><span class="sxs-lookup"><span data-stu-id="cec3e-131">In this example, an exception is thrown after the flight is reserved but before the manager approval step.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 <span data-ttu-id="cec3e-132">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="cec3e-132">This example is the workflow in XAML.</span></span>  
  
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
  
 <span data-ttu-id="cec3e-133">Если вызывается рабочий процесс, исключение смоделированного условия ошибки обрабатывается ведущим приложением в <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, рабочий процесс отменяется, и вызывается логика компенсации.</span><span class="sxs-lookup"><span data-stu-id="cec3e-133">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the compensation logic is invoked.</span></span>  
  
 <span data-ttu-id="cec3e-134">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-134">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="cec3e-135">**ИмитированноеОшибкаОшибка: Бросок приложенияИсключение.** 
 **Необработанное исключение рабочего процесса:**
**System.ApplicationException: Смоделированное условие ошибки в рабочем процессе.** 
 **Отмена рейса: Билет отменяется.** 
 **Рабочий процесс успешно завершен со статусом: Отменен.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-135">**SimulatedErrorCondition: Throwing an ApplicationException.**
**Workflow Unhandled Exception:**
**System.ApplicationException: Simulated error condition in the workflow.**
**CancelFlight: Ticket is canceled.**
**Workflow completed successfully with status: Canceled.**</span></span>
### <a name="cancellation-and-compensableactivity"></a><span data-ttu-id="cec3e-136">Отмена и CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="cec3e-136">Cancellation and CompensableActivity</span></span>  
 <span data-ttu-id="cec3e-137">Если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> не завершены, и действие отменено, выполняются действия в обработчике <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-137">If the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled, the activities in the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> are executed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cec3e-138">Обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> вызывается, только если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> не завершены, и действие отменено.</span><span class="sxs-lookup"><span data-stu-id="cec3e-138">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is only invoked if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled.</span></span> <span data-ttu-id="cec3e-139">Обработчик <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> выполняется, только если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> успешно завершены, после чего на действии вызвана компенсация.</span><span class="sxs-lookup"><span data-stu-id="cec3e-139">The <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> is only executed if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have successfully completed and compensation is subsequently invoked on the activity.</span></span>  
  
 <span data-ttu-id="cec3e-140">Обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> предоставляет разработчикам рабочего процесса возможность предоставить соответствующую логику отмены.</span><span class="sxs-lookup"><span data-stu-id="cec3e-140">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gives workflow authors the opportunity to provide any appropriate cancellation logic.</span></span> <span data-ttu-id="cec3e-141">В следующем примере во время выполнения <xref:System.Activities.Statements.CompensableActivity.Body%2A> создается исключение, а затем вызывается обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-141">In the following example, an exception is thrown during the execution of the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, and then the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is invoked.</span></span>  
  
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
  
 <span data-ttu-id="cec3e-142">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="cec3e-142">This example is the workflow in XAML</span></span>  
  
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
  
 <span data-ttu-id="cec3e-143">Если вызывается рабочий процесс, исключение смоделированного условия ошибки обрабатывается ведущим приложением в <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, рабочий процесс отменяется, и вызывается логика отмены объекта <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-143">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the cancellation logic of the <xref:System.Activities.Statements.CompensableActivity> is invoked.</span></span> <span data-ttu-id="cec3e-144">В этом примере логика компенсации и логика отмены имеют различные задачи.</span><span class="sxs-lookup"><span data-stu-id="cec3e-144">In this example, the compensation logic and the cancellation logic have different goals.</span></span> <span data-ttu-id="cec3e-145">Успешное завершение <xref:System.Activities.Statements.CompensableActivity.Body%2A> означает, что с кредитной карты были списаны средства, а авиабилет заказан, поэтому компенсация должна отменить оба шага.</span><span class="sxs-lookup"><span data-stu-id="cec3e-145">If the <xref:System.Activities.Statements.CompensableActivity.Body%2A> completed successfully, then this means the credit card was charged and the flight booked, so the compensation should undo both steps.</span></span> <span data-ttu-id="cec3e-146">(В этом примере отмена рейса автоматически отменяет платежи по кредитной карте.) Однако, <xref:System.Activities.Statements.CompensableActivity> если отменен, это <xref:System.Activities.Statements.CompensableActivity.Body%2A> означает, что не завершена, и поэтому логика <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> потребностей, чтобы быть в состоянии определить, как наилучшим образом справиться с отменой.</span><span class="sxs-lookup"><span data-stu-id="cec3e-146">(In this example, canceling the flight automatically cancels the credit card charges.) However, if the <xref:System.Activities.Statements.CompensableActivity> is canceled, this means the <xref:System.Activities.Statements.CompensableActivity.Body%2A> did not complete and so the logic of the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> needs to be able to determine how to best handle the cancellation.</span></span> <span data-ttu-id="cec3e-147">В этом примере <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> отменяет начисление обязательства на кредитную карту, но, поскольку `ReserveFlight` было последним действием в <xref:System.Activities.Statements.CompensableActivity.Body%2A>, попытка отмены авиабилета не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cec3e-147">In this example, the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancels the credit card charge, but since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, it does not attempt to cancel the flight.</span></span> <span data-ttu-id="cec3e-148">Поскольку `ReserveFlight` было последним действием в <xref:System.Activities.Statements.CompensableActivity.Body%2A>, если оно успешно завершилось, то <xref:System.Activities.Statements.CompensableActivity.Body%2A> также завершилась и отмена невозможна.</span><span class="sxs-lookup"><span data-stu-id="cec3e-148">Since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, if it had successfully completed then the <xref:System.Activities.Statements.CompensableActivity.Body%2A> would have completed and no cancellation would be possible.</span></span>  
  
 <span data-ttu-id="cec3e-149">**ChargeCreditCard: начисление обязательства на кредитную карту за авиабилет.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-149">**ChargeCreditCard: Charge credit card for flight.**</span></span>  
<span data-ttu-id="cec3e-150">**ИмитированноеОшибкаОшибка: Бросок приложенияИсключение.** 
 **Необработанное исключение рабочего процесса:**
**System.ApplicationException: Смоделированное условие ошибки в рабочем процессе.** 
 **CancelCreditCard: Отмена платежей по кредитной карте.** 
 **Рабочий процесс успешно завершен со статусом: Отменен.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-150">**SimulatedErrorCondition: Throwing an ApplicationException.**
**Workflow Unhandled Exception:**
**System.ApplicationException: Simulated error condition in the workflow.**
**CancelCreditCard: Cancel credit card charges.**
**Workflow completed successfully with status: Canceled.**</span></span>  <span data-ttu-id="cec3e-151">Для получения дополнительной информации об отмене [см.](modeling-cancellation-behavior-in-workflows.md)</span><span class="sxs-lookup"><span data-stu-id="cec3e-151">For more information about cancellation, see [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a><span data-ttu-id="cec3e-152">Явная компенсация с использованием действия компенсации</span><span class="sxs-lookup"><span data-stu-id="cec3e-152">Explicit Compensation Using the Compensate Activity</span></span>  
 <span data-ttu-id="cec3e-153">В предыдущем разделе была описана неявная компенсация.</span><span class="sxs-lookup"><span data-stu-id="cec3e-153">In the previous section, implicit compensation was covered.</span></span> <span data-ttu-id="cec3e-154">Неявная компенсация может использоваться в простых сценариях, но если требуется более явный контроль над планированием обработки компенсации, можно использовать действие <xref:System.Activities.Statements.Compensate>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-154">Implicit compensation can be appropriate for simple scenarios, but if more explicit control is required over the scheduling of compensation handling then the <xref:System.Activities.Statements.Compensate> activity can be used.</span></span> <span data-ttu-id="cec3e-155">Для инициации процесса компенсации с применением действия <xref:System.Activities.Statements.Compensate> используется маркер <xref:System.Activities.Statements.CompensationToken> действия <xref:System.Activities.Statements.CompensableActivity>, для которого необходимо провести компенсацию.</span><span class="sxs-lookup"><span data-stu-id="cec3e-155">To initiate the compensation process with the <xref:System.Activities.Statements.Compensate> activity, the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> for which compensation is desired is used.</span></span> <span data-ttu-id="cec3e-156">Действие <xref:System.Activities.Statements.Compensate> может использоваться для запуска компенсации для любого выполненного действия <xref:System.Activities.Statements.CompensableActivity>, которое не было подтверждено или компенсировано.</span><span class="sxs-lookup"><span data-stu-id="cec3e-156">The <xref:System.Activities.Statements.Compensate> activity can be used to initiate compensation on any completed <xref:System.Activities.Statements.CompensableActivity> that has not been confirmed or compensated.</span></span> <span data-ttu-id="cec3e-157">Например, действие <xref:System.Activities.Statements.Compensate> может использоваться в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A> действия <xref:System.Activities.Statements.TryCatch> или в любой момент после завершения действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-157">For example, a <xref:System.Activities.Statements.Compensate> activity could be used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity, or any time after the <xref:System.Activities.Statements.CompensableActivity> has completed.</span></span> <span data-ttu-id="cec3e-158">В данном примере действие <xref:System.Activities.Statements.Compensate> используется в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A> действия <xref:System.Activities.Statements.TryCatch> для обращения действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-158">In this example, the <xref:System.Activities.Statements.Compensate> activity is used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity to reverse the action of the <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 <span data-ttu-id="cec3e-159">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="cec3e-159">This example is the workflow in XAML.</span></span>  
  
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
  
 <span data-ttu-id="cec3e-160">При вызове рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="cec3e-160">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="cec3e-161">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-161">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="cec3e-162">**ИмитированноеОшибкаОшибка: Бросок приложенияИсключение.** 
 **Отмена рейса: Билет отменяется.** 
 **Рабочий процесс успешно завершен со статусом: Закрыто.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-162">**SimulatedErrorCondition: Throwing an ApplicationException.**
**CancelFlight: Ticket is canceled.**
**Workflow completed successfully with status: Closed.**</span></span>
### <a name="confirming-compensation"></a><span data-ttu-id="cec3e-163">Подтверждение компенсации</span><span class="sxs-lookup"><span data-stu-id="cec3e-163">Confirming Compensation</span></span>  
 <span data-ttu-id="cec3e-164">По умолчанию подлежащие компенсации действия могут быть компенсированы в любой момент после их завершения.</span><span class="sxs-lookup"><span data-stu-id="cec3e-164">By default, compensable activities can be compensated any time after they have completed.</span></span> <span data-ttu-id="cec3e-165">Но в некоторых ситуациях это может быть невозможно.</span><span class="sxs-lookup"><span data-stu-id="cec3e-165">In some scenarios this may not be appropriate.</span></span> <span data-ttu-id="cec3e-166">В предыдущем примере компенсацией для бронирования авиабилета служит отмена бронирования.</span><span class="sxs-lookup"><span data-stu-id="cec3e-166">In the previous example the compensation to reserving the ticket was to cancel the reservation.</span></span> <span data-ttu-id="cec3e-167">Однако после выполнения перелета такой шаг компенсации уже недопустим.</span><span class="sxs-lookup"><span data-stu-id="cec3e-167">However, after the flight has been completed this compensation step is no longer valid.</span></span> <span data-ttu-id="cec3e-168">Подтверждение подлежащего компенсации действия вызывает действие, заданное обработчиком <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-168">Confirming the compensable activity invokes the activity specified by the <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span></span> <span data-ttu-id="cec3e-169">Это может использоваться, например, для освобождения любых ресурсов, которые требуются при выполнении компенсации.</span><span class="sxs-lookup"><span data-stu-id="cec3e-169">One possible use for this is to allow any resources that are necessary to perform the compensation to be released.</span></span> <span data-ttu-id="cec3e-170">После подтверждения действия, которое могло быть компенсировано, его компенсация становится невозможной, и при попытке такой компенсации возникнет исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-170">After a compensable activity is confirmed it is not possible for it to be compensated, and if this is attempted an <xref:System.InvalidOperationException> exception is thrown.</span></span> <span data-ttu-id="cec3e-171">Если рабочий процесс завершается успешно, все неподтвержденные и некомпенсированные действия, завершенные успешно, подтверждаются в порядке, обратном порядку их завершения.</span><span class="sxs-lookup"><span data-stu-id="cec3e-171">When a workflow completes successfully, all non-confirmed and non-compensated compensable activities that completed successfully are confirmed in reverse order of completion.</span></span> <span data-ttu-id="cec3e-172">В данном примере авиабилет бронируется, приобретается и завершается, после чего выполняется подтверждение действия, подлежащего компенсации.</span><span class="sxs-lookup"><span data-stu-id="cec3e-172">In this example the flight is reserved, purchased, and completed, and then the compensable activity is confirmed.</span></span> <span data-ttu-id="cec3e-173">Для подтверждения действия <xref:System.Activities.Statements.CompensableActivity> следует использовать действие <xref:System.Activities.Statements.Confirm> и задать маркер <xref:System.Activities.Statements.CompensationToken> действия <xref:System.Activities.Statements.CompensableActivity>, подлежащего подтверждению.</span><span class="sxs-lookup"><span data-stu-id="cec3e-173">To confirm a <xref:System.Activities.Statements.CompensableActivity>, use the <xref:System.Activities.Statements.Confirm> activity and specify the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> to confirm.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 <span data-ttu-id="cec3e-174">Этот пример является рабочим процессом в XAML.</span><span class="sxs-lookup"><span data-stu-id="cec3e-174">This example is the workflow in XAML.</span></span>  
  
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
  
<span data-ttu-id="cec3e-175">При вызове рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="cec3e-175">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
<span data-ttu-id="cec3e-176">**ReserveFlight: Билет зарезервирован.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-176">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="cec3e-177">**ManagerApproval: Менеджер одобрение получено.** 
 **PurchaseFlight: Билет приобретается.** 
 **TakeFlight: Полет завершен.** 
 **ConfirmFlight: Полет был взят, компенсация невозможна.** 
 **Рабочий процесс успешно завершен со статусом: Закрыто.**</span><span class="sxs-lookup"><span data-stu-id="cec3e-177">**ManagerApproval: Manager approval received.**
**PurchaseFlight: Ticket is purchased.**
**TakeFlight: Flight is completed.**
**ConfirmFlight: Flight has been taken, no compensation possible.**
**Workflow completed successfully with status: Closed.**</span></span>

## <a name="nesting-compensation-activities"></a><span data-ttu-id="cec3e-178">Вложенные действия компенсации</span><span class="sxs-lookup"><span data-stu-id="cec3e-178">Nesting Compensation Activities</span></span>  

<span data-ttu-id="cec3e-179">Действие <xref:System.Activities.Statements.CompensableActivity> может быть помещено в раздел <xref:System.Activities.Statements.CompensableActivity.Body%2A> другого действия <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-179">A <xref:System.Activities.Statements.CompensableActivity> can be placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> section of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="cec3e-180">Объект <xref:System.Activities.Statements.CompensableActivity> не может быть помещен в обработчик другого <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="cec3e-180">A <xref:System.Activities.Statements.CompensableActivity> may not be placed into a handler of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="cec3e-181">Родительское действие <xref:System.Activities.Statements.CompensableActivity> обязано убедиться в том, что при отмене, подтверждении или компенсации все дочерние действия, подлежащие компенсации, которые успешно завершились и еще не подтверждены и не компенсированы, должны быть подтверждены или компенсированы перед тем, как родительское действие завершит отмену, подтверждение или компенсацию.</span><span class="sxs-lookup"><span data-stu-id="cec3e-181">It is the responsibility of a parent <xref:System.Activities.Statements.CompensableActivity> to ensure that when it is canceled, confirmed, or compensated, all child compensable activities that have completed successfully and have not already been confirmed or compensated must be confirmed or compensated before the parent completes cancellation, confirmation, or compensation.</span></span> <span data-ttu-id="cec3e-182">Если это не моделируется явным образом, родительское действие <xref:System.Activities.Statements.CompensableActivity> неявно компенсирует дочерние действия, подлежащие компенсации, если получит сигнал отмены или компенсации.</span><span class="sxs-lookup"><span data-stu-id="cec3e-182">If this is not modeled explicitly the parent <xref:System.Activities.Statements.CompensableActivity> will implicitly compensate child compensable activities if the parent received the cancel or compensate signal.</span></span> <span data-ttu-id="cec3e-183">Если родитель получил сигнал подтверждения, родитель неявно подтвердит дочерние действия, подлежащие компенсации.</span><span class="sxs-lookup"><span data-stu-id="cec3e-183">If the parent received the confirm signal the parent will implicitly confirm child compensable activities.</span></span> <span data-ttu-id="cec3e-184">Если логика обработки отмены, подтверждения или компенсации явным образом моделируется в обработчике родительского <xref:System.Activities.Statements.CompensableActivity>, то любое явно не обработанное дочернее действие будет неявно подтверждено.</span><span class="sxs-lookup"><span data-stu-id="cec3e-184">If the logic to handle cancellation, confirmation, or compensation is explicitly modeled in the handler of the parent <xref:System.Activities.Statements.CompensableActivity>, any child not explicitly handled will be implicitly confirmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec3e-185">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cec3e-185">See also</span></span>

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
