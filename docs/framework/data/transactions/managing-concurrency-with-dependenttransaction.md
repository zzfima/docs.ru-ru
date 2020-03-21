---
title: Управление параллелизмом с помощью класса DependentTransaction
ms.date: 03/30/2017
ms.assetid: b85a97d8-8e02-4555-95df-34c8af095148
ms.openlocfilehash: a8ddcab4b065c3400f9f9f7ec9ce04befdd0f29b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174385"
---
# <a name="managing-concurrency-with-dependenttransaction"></a><span data-ttu-id="64cb4-102">Управление параллелизмом с помощью класса DependentTransaction</span><span class="sxs-lookup"><span data-stu-id="64cb4-102">Managing Concurrency with DependentTransaction</span></span>
<span data-ttu-id="64cb4-103">Объект <xref:System.Transactions.Transaction> создается с помощью метода <xref:System.Transactions.Transaction.DependentClone%2A>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-103">The <xref:System.Transactions.Transaction> object is created using the <xref:System.Transactions.Transaction.DependentClone%2A> method.</span></span> <span data-ttu-id="64cb4-104">Его единственная цель — гарантировать невозможность фиксации транзакции, пока некоторые фрагменты кода (например рабочий поток) еще выполняют операции над транзакцией.</span><span class="sxs-lookup"><span data-stu-id="64cb4-104">Its sole purpose is to guarantee that the transaction cannot commit while some other pieces of code (for example, a worker thread) are still performing work on the transaction.</span></span> <span data-ttu-id="64cb4-105">Когда операции в рамках клонированной транзакции завершены и готовы к фиксации, создателю транзакции может быть передано соответствующее уведомление с помощью метода <xref:System.Transactions.DependentTransaction.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-105">When the work done within the cloned transaction is complete and ready to be committed, it can notify the creator of the transaction using the <xref:System.Transactions.DependentTransaction.Complete%2A> method.</span></span> <span data-ttu-id="64cb4-106">Это позволяет сохранить согласованность и правильность данных.</span><span class="sxs-lookup"><span data-stu-id="64cb4-106">Thus, you can preserve the consistency and correctness of data.</span></span>  
  
 <span data-ttu-id="64cb4-107">Класс <xref:System.Transactions.DependentTransaction> также можно использовать для управления параллелизмом при выполнении асинхронных задач.</span><span class="sxs-lookup"><span data-stu-id="64cb4-107">The <xref:System.Transactions.DependentTransaction> class can also be used to manage concurrency between asynchronous tasks.</span></span> <span data-ttu-id="64cb4-108">В этом сценарии родительская транзакция может продолжать выполнение любого кода, пока ее зависимый клон выполняет свои задачи.</span><span class="sxs-lookup"><span data-stu-id="64cb4-108">In this scenario, the parent can continue to execute any code while the dependent clone works on its own tasks.</span></span> <span data-ttu-id="64cb4-109">Другими словами, выполнение родительской транзакции не блокируется до завершения выполнения зависимого клона.</span><span class="sxs-lookup"><span data-stu-id="64cb4-109">In other words, the parent's execution is not blocked until the dependent completes.</span></span>  
  
## <a name="creating-a-dependent-clone"></a><span data-ttu-id="64cb4-110">Создание зависимого клона</span><span class="sxs-lookup"><span data-stu-id="64cb4-110">Creating a Dependent Clone</span></span>  
 <span data-ttu-id="64cb4-111">Чтобы создать зависимую транзакцию, вызовите метод <xref:System.Transactions.Transaction.DependentClone%2A>, передав ему в качестве параметра перечисление <xref:System.Transactions.DependentCloneOption>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-111">To create a dependent transaction, call the <xref:System.Transactions.Transaction.DependentClone%2A> method and pass the <xref:System.Transactions.DependentCloneOption> enumeration as a parameter.</span></span> <span data-ttu-id="64cb4-112">Этот параметр определяет поведение транзакции, когда метод `Commit` родительской транзакции вызывается до того, как зависимый клон указывает, что он готов к фиксации транзакции (путем вызова метода <xref:System.Transactions.DependentTransaction.Complete%2A>).</span><span class="sxs-lookup"><span data-stu-id="64cb4-112">This parameter defines the behavior of the transaction if `Commit` is called on the parent transaction before the dependent clone indicates that it is ready for the transaction to commit (by calling the <xref:System.Transactions.DependentTransaction.Complete%2A> method).</span></span> <span data-ttu-id="64cb4-113">Этот параметр может принимать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="64cb4-113">The following values are valid for this parameter:</span></span>  
  
- <span data-ttu-id="64cb4-114"><xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>создает зависимую транзакцию, которая блокирует процесс фиксации родительской транзакции до тех пор, пока транзакция родительского отсечку не выйдет из-под ожидания, или пока не <xref:System.Transactions.DependentTransaction.Complete%2A> будет вызвана на всех иждивенцев, указывающих на их завершение.</span><span class="sxs-lookup"><span data-stu-id="64cb4-114"><xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete> creates a dependent transaction that blocks the commit process of the parent transaction until the parent transaction times out, or until <xref:System.Transactions.DependentTransaction.Complete%2A> is called on all dependents indicating their completion.</span></span> <span data-ttu-id="64cb4-115">Этот параметр полезно использовать, когда фиксация транзакции должна быть выполнена только после завершения зависимых транзакций.</span><span class="sxs-lookup"><span data-stu-id="64cb4-115">This is useful when the client does not want the parent transaction to commit until the dependent transactions have completed.</span></span> <span data-ttu-id="64cb4-116">Если родительская транзакция завершает свои операции раньше зависимой транзакции и вызывает метод <xref:System.Transactions.CommittableTransaction.Commit%2A>, процесс фиксации блокируется для выполнения над транзакцией дополнительных операций и создания новых зачислений; блокировка снимается, когда все зависимые транзакции вызовут метод <xref:System.Transactions.DependentTransaction.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-116">If the parent finishes its work earlier than the dependent transaction and calls <xref:System.Transactions.CommittableTransaction.Commit%2A> on the transaction, the commit process is blocked in a state where additional work can be done on the transaction and new enlistments can be created, until all of the dependents call <xref:System.Transactions.DependentTransaction.Complete%2A>.</span></span> <span data-ttu-id="64cb4-117">Когда все зависимые транзакции завершат свои операции и вызовут метод <xref:System.Transactions.DependentTransaction.Complete%2A>, начинается процесс фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="64cb4-117">As soon as all of them have finished their work and call <xref:System.Transactions.DependentTransaction.Complete%2A>, the commit process for the transaction begins.</span></span>  
  
- <span data-ttu-id="64cb4-118"><xref:System.Transactions.DependentCloneOption.RollbackIfNotComplete>. Этот параметр, напротив, позволяет создать зависимую транзакцию, которая автоматически прерывается, если метод <xref:System.Transactions.CommittableTransaction.Commit%2A> родительской транзакции вызывается до метода <xref:System.Transactions.DependentTransaction.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-118"><xref:System.Transactions.DependentCloneOption.RollbackIfNotComplete>, on the other hand, creates a dependent transaction that automatically aborts if <xref:System.Transactions.CommittableTransaction.Commit%2A> is called on the parent transaction before <xref:System.Transactions.DependentTransaction.Complete%2A> is called.</span></span> <span data-ttu-id="64cb4-119">В этом случае все операции зависимой транзакции выполняются как один блок, который нельзя зафиксировать частично.</span><span class="sxs-lookup"><span data-stu-id="64cb4-119">In this case, all the work done in the dependent transaction is intact within one transaction lifetime, and no one has a chance to commit just a portion of it.</span></span>  
  
 <span data-ttu-id="64cb4-120">Метод <xref:System.Transactions.DependentTransaction.Complete%2A> должен быть вызван только один раз после завершения обработки зависимой транзакции приложением; в противном случае возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-120">The <xref:System.Transactions.DependentTransaction.Complete%2A> method must be called only once when your application finishes its work on the dependent transaction; otherwise, a <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="64cb4-121">Попытка выполнить какие-либо дополнительные операции над транзакцией после вызова этого метода приведет к возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="64cb4-121">After this call is invoked, you must not attempt any additional work on the transaction, or an exception is thrown.</span></span>  
  
 <span data-ttu-id="64cb4-122">В следующем примере кода показано, как создать зависимую транзакцию для управления двумя параллельными задачами путем клонирования текущей транзакции и передачи клона рабочему потоку.</span><span class="sxs-lookup"><span data-stu-id="64cb4-122">The following code example shows how to create a dependent transaction to manage two concurrent tasks by cloning a dependent transaction and passing it to a worker thread.</span></span>  
  
```csharp  
public class WorkerThread  
{  
    public void DoWork(DependentTransaction dependentTransaction)  
    {  
        Thread thread = new Thread(ThreadMethod);  
        thread.Start(dependentTransaction);
    }  
  
    public void ThreadMethod(object transaction)
    {
        DependentTransaction dependentTransaction = transaction as DependentTransaction;  
        Debug.Assert(dependentTransaction != null);
        try  
        {  
            using(TransactionScope ts = new TransactionScope(dependentTransaction))  
            {  
                /* Perform transactional work here */
                ts.Complete();  
            }  
        }  
        finally  
        {  
            dependentTransaction.Complete();
             dependentTransaction.Dispose();
        }  
    }  
  
//Client code
using(TransactionScope scope = new TransactionScope())  
{  
    Transaction currentTransaction = Transaction.Current;  
    DependentTransaction dependentTransaction;
    dependentTransaction = currentTransaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
    WorkerThread workerThread = new WorkerThread();  
    workerThread.DoWork(dependentTransaction);  
    /* Do some transactional work here, then: */  
    scope.Complete();  
}  
```  
  
 <span data-ttu-id="64cb4-123">Клиентский код создает область транзакции, которая также задает внешнюю транзакцию.</span><span class="sxs-lookup"><span data-stu-id="64cb4-123">The client code creates a transactional scope that also sets the ambient transaction.</span></span> <span data-ttu-id="64cb4-124">Не следует передавать внешнюю транзакцию рабочему потоку.</span><span class="sxs-lookup"><span data-stu-id="64cb4-124">You should not pass the ambient transaction to the worker thread.</span></span> <span data-ttu-id="64cb4-125">Вместо этого следует клонировать текущую (внешнюю) транзакцию путем вызова метода <xref:System.Transactions.Transaction.DependentClone%2A> для текущей транзакции и передачи зависимой транзакции рабочему потоку.</span><span class="sxs-lookup"><span data-stu-id="64cb4-125">Instead, you should clone the current (ambient) transaction by calling the <xref:System.Transactions.Transaction.DependentClone%2A> method on the current transaction, and pass the dependent to the worker thread.</span></span>  
  
 <span data-ttu-id="64cb4-126">Метод `ThreadMethod` выполняется в новом потоке.</span><span class="sxs-lookup"><span data-stu-id="64cb4-126">The `ThreadMethod` method executes on the new thread.</span></span> <span data-ttu-id="64cb4-127">Клиентский код запускает новый поток, передавая зависимую транзакцию в качестве параметра `ThreadMethod`.</span><span class="sxs-lookup"><span data-stu-id="64cb4-127">The client starts a new thread, passing the dependent transaction as the `ThreadMethod` parameter.</span></span>  
  
 <span data-ttu-id="64cb4-128">Поскольку зависимая транзакция создается с параметром <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>, исходная транзакция может быть зафиксирована только после завершения всех операций во втором потоке и вызова метода <xref:System.Transactions.DependentTransaction.Complete%2A> зависимой транзакции.</span><span class="sxs-lookup"><span data-stu-id="64cb4-128">Because the dependent transaction is created with <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>, you are guaranteed that the transaction cannot be committed until all of the transactional work done on the second thread is finished and <xref:System.Transactions.DependentTransaction.Complete%2A> is called on the dependent transaction.</span></span> <span data-ttu-id="64cb4-129">Это означает, что если область действия клиента заканчивается (когда он пытается `using` избавиться от объекта <xref:System.Transactions.DependentTransaction.Complete%2A> транзакции в конце оператора) <xref:System.Transactions.DependentTransaction.Complete%2A> до того, как новый поток вызывает зависимую транзакцию, клиентский код блокируется до тех пор, пока он не будет вызван зависимым.</span><span class="sxs-lookup"><span data-stu-id="64cb4-129">This means that if the client's scope ends (when it tries to dispose of the transaction object at the end of the `using` statement) before the new thread calls <xref:System.Transactions.DependentTransaction.Complete%2A> on the dependent transaction, the client code blocks until <xref:System.Transactions.DependentTransaction.Complete%2A> is called on the dependent.</span></span> <span data-ttu-id="64cb4-130">После этого может быть завершен процесс фиксации или прерывания транзакции.</span><span class="sxs-lookup"><span data-stu-id="64cb4-130">Then the transaction can finish committing or aborting.</span></span>  
  
## <a name="concurrency-issues"></a><span data-ttu-id="64cb4-131">Проблемы параллелизма</span><span class="sxs-lookup"><span data-stu-id="64cb4-131">Concurrency Issues</span></span>  
 <span data-ttu-id="64cb4-132">При использовании класса <xref:System.Transactions.DependentTransaction> следует помнить о нескольких дополнительных проблемах параллелизма.</span><span class="sxs-lookup"><span data-stu-id="64cb4-132">There are a few additional concurrency issues that you need to be aware of when using the <xref:System.Transactions.DependentTransaction> class:</span></span>  
  
- <span data-ttu-id="64cb4-133">Если рабочий поток откатывает транзакцию, а родительская транзакция пытается ее зафиксировать, возникает исключение <xref:System.Transactions.TransactionAbortedException>.</span><span class="sxs-lookup"><span data-stu-id="64cb4-133">If the worker thread rolls back the transaction but the parent tries to commit it, a <xref:System.Transactions.TransactionAbortedException> is thrown.</span></span>  
  
- <span data-ttu-id="64cb4-134">Для каждого рабочего потока в транзакции следует создавать новый зависимый клон.</span><span class="sxs-lookup"><span data-stu-id="64cb4-134">You should create a new dependent clone for each worker thread in the transaction.</span></span> <span data-ttu-id="64cb4-135">Не следует передавать один и тот же зависимый клон нескольким потокам, поскольку только один из них может вызвать метод <xref:System.Transactions.DependentTransaction.Complete%2A> зависимого клона.</span><span class="sxs-lookup"><span data-stu-id="64cb4-135">Do not pass the same dependent clone to multiple threads, because only one of them can call <xref:System.Transactions.DependentTransaction.Complete%2A> on it.</span></span>  
  
- <span data-ttu-id="64cb4-136">Если рабочий поток порождает новый рабочий поток, следует создать новый зависимый клон из существующего зависимого клона и передать его новому потоку.</span><span class="sxs-lookup"><span data-stu-id="64cb4-136">If the worker thread spawns a new worker thread, make sure to create a dependent clone from the dependent clone and pass it to the new thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cb4-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64cb4-137">See also</span></span>

- <xref:System.Transactions.DependentTransaction>
