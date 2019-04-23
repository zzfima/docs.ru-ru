---
title: Однофазная и многофазная фиксация транзакции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
ms.openlocfilehash: cbe00fb792ab5f2a7586a958ddbe5bdf004656dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089566"
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="66fbf-102">Однофазная и многофазная фиксация транзакции</span><span class="sxs-lookup"><span data-stu-id="66fbf-102">Committing a Transaction in Single-Phase and Multi-Phase</span></span>
<span data-ttu-id="66fbf-103">Каждым используемым в транзакции ресурсом управляет диспетчер ресурсов, действия которого координируются диспетчером транзакций.</span><span class="sxs-lookup"><span data-stu-id="66fbf-103">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="66fbf-104">[Ресурсы прикрепление в транзакции, в качестве участников](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) разделе рассматривается, как можно прикрепить ресурс (или несколько ресурсов) в транзакции.</span><span class="sxs-lookup"><span data-stu-id="66fbf-104">The [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="66fbf-105">В этом разделе также описывается порядок координации процесса фиксации транзакции между зачисленными ресурсами.</span><span class="sxs-lookup"><span data-stu-id="66fbf-105">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="66fbf-106">При завершении транзакции приложение формирует запрос на фиксацию или откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="66fbf-106">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="66fbf-107">Диспетчер транзакций должен исключить ситуации, в которых один из диспетчеров ресурсов голосует за фиксацию, а другие - за откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="66fbf-107">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="66fbf-108">Если транзакция включает несколько ресурсов, необходимо выполнить двухфазную фиксацию (2PC).</span><span class="sxs-lookup"><span data-stu-id="66fbf-108">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="66fbf-109">Протокол двухфазной фиксации (фаза подготовки и фаза фиксации) гарантирует, что при завершении транзакции все изменения, произведенные над всеми ресурсами, либо полностью фиксируются, либо полностью откатываются.</span><span class="sxs-lookup"><span data-stu-id="66fbf-109">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="66fbf-110">После завершения транзакции результат сообщается всем участникам.</span><span class="sxs-lookup"><span data-stu-id="66fbf-110">All the participants are then informed of the final result.</span></span> <span data-ttu-id="66fbf-111">Подробное описание протокола двухфазной фиксации, см. в книге «*обработки транзакций: Основные понятия и методы (серия Morgan kaufmann по системам управления данными) ISBN: 1558601902*«, Джим Грей.</span><span class="sxs-lookup"><span data-stu-id="66fbf-111">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="66fbf-112">Кроме того, оптимизировать производительность транзакции можно путем участия в протоколе однофазной фиксации.</span><span class="sxs-lookup"><span data-stu-id="66fbf-112">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="66fbf-113">Дополнительные сведения см. в разделе [оптимизация производительности с помощью однофазной фиксации и повышаемого однофазного уведомления](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="66fbf-113">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="66fbf-114">Если требуется только получение информации о результате транзакции без участия в голосовании, необходимо подписаться на событие <xref:System.Transactions.Transaction.TransactionCompleted>.</span><span class="sxs-lookup"><span data-stu-id="66fbf-114">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="66fbf-115">Двухфазная фиксация (2PC)</span><span class="sxs-lookup"><span data-stu-id="66fbf-115">Two-phase Commit (2PC)</span></span>  
 <span data-ttu-id="66fbf-116">В первой фазе транзакции диспетчер транзакций опрашивает каждый ресурс, чтобы определить, следует ли выполнить фиксацию или откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="66fbf-116">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="66fbf-117">Во второй фазе транзакции диспетчер транзакций уведомляет каждый ресурс о результате опроса, позволяя ресурсам выполнить необходимые операции очистки.</span><span class="sxs-lookup"><span data-stu-id="66fbf-117">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="66fbf-118">Для участия в такой транзакции диспетчеру ресурсов необходимо реализовать интерфейс <xref:System.Transactions.IEnlistmentNotification>, который предоставляет методы, вызываемые диспетчером транзакций как уведомления при двухфазной фиксации.</span><span class="sxs-lookup"><span data-stu-id="66fbf-118">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="66fbf-119">Ниже представлен пример такой реализации.</span><span class="sxs-lookup"><span data-stu-id="66fbf-119">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="66fbf-120">Фаза подготовки (фаза 1)</span><span class="sxs-lookup"><span data-stu-id="66fbf-120">Prepare phase (Phase 1)</span></span>  
 <span data-ttu-id="66fbf-121">При получении запроса <xref:System.Transactions.CommittableTransaction.Commit%2A> от приложения диспетчер транзакций приступает к фазе подготовки всех зачисленных участников путем вызова метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> для каждого зачисленного ресурса с целью получения голосов за результат транзакции.</span><span class="sxs-lookup"><span data-stu-id="66fbf-121">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="66fbf-122">Диспетчеру ресурсов, реализующему интерфейс <xref:System.Transactions.IEnlistmentNotification>, сначала необходимо реализовать метод <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29>, как показано в следующем простом примере.</span><span class="sxs-lookup"><span data-stu-id="66fbf-122">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```csharp
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="66fbf-123">После получения этого вызова диспетчеру устойчивых ресурсов необходимо записать в журнал данные для восстановления транзакции (доступ к которым осуществляется путем извлечения свойства <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>) и всю необходимую информацию для завершения транзакции фиксацией.</span><span class="sxs-lookup"><span data-stu-id="66fbf-123">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="66fbf-124">Запись этой информации в рамках метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> не требуется, поскольку диспетчер ресурсов может сделать это в рабочем потоке.</span><span class="sxs-lookup"><span data-stu-id="66fbf-124">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="66fbf-125">После того, как диспетчер ресурсов завершил свои операции подготовки, ему необходимо проголосовать за фиксацию или откат путем вызова метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A> или <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>.</span><span class="sxs-lookup"><span data-stu-id="66fbf-125">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="66fbf-126">Обратите внимание, что класс <xref:System.Transactions.PreparingEnlistment> наследует метод <xref:System.Transactions.Enlistment.Done%2A> от класса <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="66fbf-126">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="66fbf-127">Если вызвать этот метод для обратного вызова <xref:System.Transactions.PreparingEnlistment> в фазе подготовки, он сообщает диспетчеру транзакций, что зачисленный ресурс доступен в режиме "только чтение" (т. е. диспетчеры ресурсов могут читать, но не могут изменять защищенные транзакцией данные), и диспетчер ресурсов не получает дальнейших уведомлений от диспетчера транзакций относительно результата транзакции в фазе 2.</span><span class="sxs-lookup"><span data-stu-id="66fbf-127">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="66fbf-128">Приложение получает сведения об успешной подготовке к фиксации транзакции после того, как все диспетчеры ресурсов проголосуют с помощью метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span><span class="sxs-lookup"><span data-stu-id="66fbf-128">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="66fbf-129">Фаза фиксации (фаза 2)</span><span class="sxs-lookup"><span data-stu-id="66fbf-129">Commit phase (Phase 2)</span></span>  
 <span data-ttu-id="66fbf-130">Если во второй фазе транзакции диспетчер транзакций получает сведения об успешной подготовке от всех диспетчеров ресурсов (все диспетчеры ресурсов вызвали метод <xref:System.Transactions.PreparingEnlistment.Prepared%2A> в конце фазы 1), он вызывает метод <xref:System.Transactions.IEnlistmentNotification.Commit%2A> для каждого диспетчера ресурсов.</span><span class="sxs-lookup"><span data-stu-id="66fbf-130">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="66fbf-131">После этого диспетчеры ресурсов могут зафиксировать изменения.</span><span class="sxs-lookup"><span data-stu-id="66fbf-131">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="66fbf-132">Если в фазе 1 хотя бы от одного диспетчера ресурсов получено сообщение о том, что подготовку выполнить не удалось, диспетчер транзакций вызывает метод <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> для каждого диспетчера ресурсов и сообщает приложению о сбое фиксации.</span><span class="sxs-lookup"><span data-stu-id="66fbf-132">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="66fbf-133">Таким образом, используемому диспетчеру ресурсов необходимо реализовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="66fbf-133">Thus, your resource manager should implement the following methods.</span></span>  
  
```csharp
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment    
     enlistment.Done();    
}  
```  
  
 <span data-ttu-id="66fbf-134">Диспетчер ресурсов должен выполнить любые действия, необходимые для завершения транзакции в соответствии с типом уведомления, и затем информировать диспетчер транзакций о завершении транзакции, вызвав метод <xref:System.Transactions.Enlistment.Done%2A> для параметра <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="66fbf-134">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="66fbf-135">Это может быть выполнено в рабочем потоке.</span><span class="sxs-lookup"><span data-stu-id="66fbf-135">This work can be done on a worker thread.</span></span> <span data-ttu-id="66fbf-136">Заметьте, что уведомления второго этапа могут быть встроены в тот же поток, который вызвал метод <xref:System.Transactions.PreparingEnlistment.Prepared%2A> на первой фазе.</span><span class="sxs-lookup"><span data-stu-id="66fbf-136">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="66fbf-137">Таким образом, после вызова метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A> не нужно выполнять никаких действий (например, снимать блокировки), которые должны были быть выполнены перед получением уведомлений второго этапа.</span><span class="sxs-lookup"><span data-stu-id="66fbf-137">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="66fbf-138">Реализация метода InDoubt</span><span class="sxs-lookup"><span data-stu-id="66fbf-138">Implementing InDoubt</span></span>  
 <span data-ttu-id="66fbf-139">Наконец, необходимо реализовать метод <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> для диспетчера неустойчивых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="66fbf-139">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="66fbf-140">Этот метод вызывается при потере контакта диспетчера транзакций с одним или несколькими участниками, в результате чего их состояние становится неизвестным.</span><span class="sxs-lookup"><span data-stu-id="66fbf-140">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="66fbf-141">В этом случае необходимо сделать соответствующую запись в журнале, чтобы можно было позднее выяснить, остался ли кто-либо из участников транзакции в несогласованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="66fbf-141">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```csharp
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="66fbf-142">Оптимизация однофазной фиксации</span><span class="sxs-lookup"><span data-stu-id="66fbf-142">Single Phase Commit Optimization</span></span>  
 <span data-ttu-id="66fbf-143">Протокол однофазной фиксации наиболее эффективен при использовании во время выполнения, поскольку все изменения производятся без какой-либо явной координации.</span><span class="sxs-lookup"><span data-stu-id="66fbf-143">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="66fbf-144">Дополнительные сведения об этом протоколе см. в разделе [оптимизация производительности с помощью однофазной фиксации и повышаемого однофазного уведомления](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="66fbf-144">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fbf-145">См. также</span><span class="sxs-lookup"><span data-stu-id="66fbf-145">See also</span></span>

- [<span data-ttu-id="66fbf-146">Оптимизация производительности с помощью механизмов уведомления об однофазной фиксации и повышаемого однофазного присоединения</span><span class="sxs-lookup"><span data-stu-id="66fbf-146">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)
- [<span data-ttu-id="66fbf-147">Зачисление ресурсов в транзакцию в качестве участников</span><span class="sxs-lookup"><span data-stu-id="66fbf-147">Enlisting Resources as Participants in a Transaction</span></span>](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)
