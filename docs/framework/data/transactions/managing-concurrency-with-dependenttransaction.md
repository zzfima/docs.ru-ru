---
title: Управление параллелизмом с помощью класса DependentTransaction
ms.date: 03/30/2017
ms.assetid: b85a97d8-8e02-4555-95df-34c8af095148
ms.openlocfilehash: 8de7cc6257317ff7128f25968a9dcf80ae5af89d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040419"
---
# <a name="managing-concurrency-with-dependenttransaction"></a>Управление параллелизмом с помощью класса DependentTransaction
Объект <xref:System.Transactions.Transaction> создается с помощью метода <xref:System.Transactions.Transaction.DependentClone%2A>. Его единственная цель — гарантировать невозможность фиксации транзакции, пока некоторые фрагменты кода (например рабочий поток) еще выполняют операции над транзакцией. Когда операции в рамках клонированной транзакции завершены и готовы к фиксации, создателю транзакции может быть передано соответствующее уведомление с помощью метода <xref:System.Transactions.DependentTransaction.Complete%2A>. Это позволяет сохранить согласованность и правильность данных.  
  
 Класс <xref:System.Transactions.DependentTransaction> также можно использовать для управления параллелизмом при выполнении асинхронных задач. В этом сценарии родительская транзакция может продолжать выполнение любого кода, пока ее зависимый клон выполняет свои задачи. Другими словами, выполнение родительской транзакции не блокируется до завершения выполнения зависимого клона.  
  
## <a name="creating-a-dependent-clone"></a>Создание зависимого клона  
 Чтобы создать зависимую транзакцию, вызовите метод <xref:System.Transactions.Transaction.DependentClone%2A>, передав ему в качестве параметра перечисление <xref:System.Transactions.DependentCloneOption>. Этот параметр определяет поведение транзакции, когда метод `Commit` родительской транзакции вызывается до того, как зависимый клон указывает, что он готов к фиксации транзакции (путем вызова метода <xref:System.Transactions.DependentTransaction.Complete%2A>). Этот параметр может принимать следующие значения.  
  
- <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete> создает зависимую транзакцию, которая блокирует процесс фиксации родительской транзакции до истечения времени ожидания родительской транзакции, или до тех пор, пока не будет вызвана <xref:System.Transactions.DependentTransaction.Complete%2A> для всех зависимых объектов, указывающих на их завершение. Этот параметр полезно использовать, когда фиксация транзакции должна быть выполнена только после завершения зависимых транзакций. Если родительская транзакция завершает свои операции раньше зависимой транзакции и вызывает метод <xref:System.Transactions.CommittableTransaction.Commit%2A>, процесс фиксации блокируется для выполнения над транзакцией дополнительных операций и создания новых зачислений; блокировка снимается, когда все зависимые транзакции вызовут метод <xref:System.Transactions.DependentTransaction.Complete%2A>. Когда все зависимые транзакции завершат свои операции и вызовут метод <xref:System.Transactions.DependentTransaction.Complete%2A>, начинается процесс фиксации транзакции.  
  
- <xref:System.Transactions.DependentCloneOption.RollbackIfNotComplete>. Этот параметр, напротив, позволяет создать зависимую транзакцию, которая автоматически прерывается, если метод <xref:System.Transactions.CommittableTransaction.Commit%2A> родительской транзакции вызывается до метода <xref:System.Transactions.DependentTransaction.Complete%2A>. В этом случае все операции зависимой транзакции выполняются как один блок, который нельзя зафиксировать частично.  
  
 Метод <xref:System.Transactions.DependentTransaction.Complete%2A> должен быть вызван только один раз после завершения обработки зависимой транзакции приложением; в противном случае возникает исключение <xref:System.InvalidOperationException>. Попытка выполнить какие-либо дополнительные операции над транзакцией после вызова этого метода приведет к возникновению исключения.  
  
 В следующем примере кода показано, как создать зависимую транзакцию для управления двумя параллельными задачами путем клонирования текущей транзакции и передачи клона рабочему потоку.  
  
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
  
 Клиентский код создает область транзакции, которая также задает внешнюю транзакцию. Не следует передавать внешнюю транзакцию рабочему потоку. Вместо этого следует клонировать текущую (внешнюю) транзакцию путем вызова метода <xref:System.Transactions.Transaction.DependentClone%2A> для текущей транзакции и передачи зависимой транзакции рабочему потоку.  
  
 Метод `ThreadMethod` выполняется в новом потоке. Клиентский код запускает новый поток, передавая зависимую транзакцию в качестве параметра `ThreadMethod`.  
  
 Поскольку зависимая транзакция создается с параметром <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>, исходная транзакция может быть зафиксирована только после завершения всех операций во втором потоке и вызова метода <xref:System.Transactions.DependentTransaction.Complete%2A> зависимой транзакции. Это означает, что если область, созданная клиентским кодом, завершается (попыткой удаления объекта транзакции в конце оператора `using`) до вызова новым потоком метода <xref:System.Transactions.DependentTransaction.Complete%2A> зависимой транзакции, выполнение клиентского кода блокируется, пока метод <xref:System.Transactions.DependentTransaction.Complete%2A> зависимой транзакции не будет вызван. После этого может быть завершен процесс фиксации или прерывания транзакции.  
  
## <a name="concurrency-issues"></a>Проблемы параллелизма  
 При использовании класса <xref:System.Transactions.DependentTransaction> следует помнить о нескольких дополнительных проблемах параллелизма.  
  
- Если рабочий поток откатывает транзакцию, а родительская транзакция пытается ее зафиксировать, возникает исключение <xref:System.Transactions.TransactionAbortedException>.  
  
- Для каждого рабочего потока в транзакции следует создавать новый зависимый клон. Не следует передавать один и тот же зависимый клон нескольким потокам, поскольку только один из них может вызвать метод <xref:System.Transactions.DependentTransaction.Complete%2A> зависимого клона.  
  
- Если рабочий поток порождает новый рабочий поток, следует создать новый зависимый клон из существующего зависимого клона и передать его новому потоку.  
  
## <a name="see-also"></a>См. также

- <xref:System.Transactions.DependentTransaction>
