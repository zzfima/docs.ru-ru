---
title: Реализация явной транзакции с помощью класса CommittableTransaction
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
ms.openlocfilehash: f8db79db6c4a66dfe13ec936313c4cf2c3b93be5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174411"
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a>Реализация явной транзакции с помощью класса CommittableTransaction
Класс <xref:System.Transactions.CommittableTransaction> позволяет приложениям использовать транзакцию явным образом вместо неявного использования с помощью класса <xref:System.Transactions.TransactionScope>. Он полезен при создании приложений, которым требуется использовать одну и ту же транзакцию в нескольких вызовах функций или нескольких вызовах потоков. В отличие от класса <xref:System.Transactions.TransactionScope> для фиксации или прерывания транзакции модуль записи приложения должен специально вызывать методы <xref:System.Transactions.CommittableTransaction.Commit%2A> и <xref:System.Transactions.Transaction.Rollback%2A>.  
  
## <a name="overview-of-the-committabletransaction-class"></a>Общие сведения о классе CommittableTransaction  
 Класс <xref:System.Transactions.CommittableTransaction> наследуется от класса <xref:System.Transactions.Transaction>, поэтому он предоставляет все функциональные возможности последнего. Особенно полезным является метод <xref:System.Transactions.Transaction.Rollback%2A> класса <xref:System.Transactions.Transaction>, который также можно использовать для отката объекта <xref:System.Transactions.CommittableTransaction>.  
  
 Класс <xref:System.Transactions.Transaction> аналогичен классу <xref:System.Transactions.CommittableTransaction>, но не предоставляет метод `Commit`. Это позволяет передавать объект транзакции (или его клоны) другим методам (возможно, в других потоках), управляя временем фиксации транзакции. Вызываемый код способен выполнять зачисление и голосовать за фиксацию или откат транзакции, но только создатель объекта <xref:System.Transactions.CommittableTransaction> может ее зафиксировать.  
  
 При работе с классом <xref:System.Transactions.CommittableTransaction> следует учитывать следующие факты.  
  
- Создание транзакции <xref:System.Transactions.CommittableTransaction> не задает внешнюю транзакцию. Чтобы диспетчеры ресурсов работали в правильном контексте транзакции, необходимо явно задать или сбросить внешнюю транзакцию. Задать текущую внешнюю транзакцию можно путем установки статического свойства <xref:System.Transactions.Transaction.Current%2A> глобального объекта <xref:System.Transactions.Transaction>.  
  
- Объект <xref:System.Transactions.CommittableTransaction> нельзя использовать повторно. После фиксации или отката объекта <xref:System.Transactions.CommittableTransaction> его нельзя повторно использовать в транзакции. Таким образом, его нельзя задать в качестве контекста текущей внешней транзакции.  
  
## <a name="creating-a-committabletransaction"></a>Создание объекта CommittableTransaction  
 В следующем примере создается и фиксируется новый объект <xref:System.Transactions.CommittableTransaction>.  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 Создание объекта <xref:System.Transactions.CommittableTransaction> не приводит к автоматическому заданию контекста внешней транзакции. Поэтому никакая операция над диспетчером ресурсов не является частью этой транзакции. Статическое свойство <xref:System.Transactions.Transaction.Current%2A> глобального объекта <xref:System.Transactions.Transaction> используется для задания или извлечения внешней транзакции, и приложению необходимо вручную задать ее, чтобы обеспечить возможность участия диспетчеров ресурсов в транзакции. Также рекомендуется сохранить прежнюю внешнюю транзакцию и восстановить ее после завершения использования объекта <xref:System.Transactions.CommittableTransaction>.  
  
 Чтобы зафиксировать транзакцию, необходимо явно вызвать метод <xref:System.Transactions.CommittableTransaction.Commit%2A>. Чтобы откатить транзакцию, необходимо вызвать метод <xref:System.Transactions.Transaction.Rollback%2A>. Важно отметить, что пока не выполнена фиксация или откат транзакции <xref:System.Transactions.CommittableTransaction>, все задействованные в ней ресурсы заблокированы.  
  
 Объект <xref:System.Transactions.CommittableTransaction> может использоваться внешними вызовами функций и потоками. Однако при этом разработчику приложения необходимо самостоятельно обеспечить обработку исключений и явный вызов метода <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> в случае сбоев.  
  
## <a name="asynchronous-commit"></a>Асинхронная фиксация  
 Класс <xref:System.Transactions.CommittableTransaction> также предоставляет механизм для асинхронной фиксации транзакций. Фиксация транзакции может занять значительное время, поскольку она может включать несколько операций доступа к базе данных и возможны задержки в сети. Во избежание взаимоблокировок в высокопроизводительных приложениях можно использовать механизм асинхронной фиксации для завершения операций транзакции как можно скорее и выполнения операции фиксации в качестве фоновой задачи. Это можно сделать с помощью методов <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> и <xref:System.Transactions.CommittableTransaction.EndCommit%2A> класса <xref:System.Transactions.CommittableTransaction>.  
  
 Можно вызвать метод <xref:System.Transactions.CommittableTransaction.BeginCommit%2A>, чтобы передать задачу фиксации потоку из пула потоков. Кроме того, можно вызвать метод <xref:System.Transactions.CommittableTransaction.EndCommit%2A>, чтобы определить, была ли выполнена фиксация транзакции. Если фиксацию транзакции по какой-либо причине выполнить не удалось, метод <xref:System.Transactions.CommittableTransaction.EndCommit%2A> вызывает исключение. Если на момент вызова метода <xref:System.Transactions.CommittableTransaction.EndCommit%2A> транзакция не зафиксирована, вызов блокируется до фиксации или отката транзакции.  
  
 Самый простой способ выполнения асинхронной фиксации - предоставление метода обратного вызова, вызываемого при завершении фиксации. Однако метод <xref:System.Transactions.CommittableTransaction.EndCommit%2A> необходимо вызвать для исходного объекта <xref:System.Transactions.CommittableTransaction>, который использовался для активизации вызова. Чтобы получить этот объект, можно ухудшить параметр *IAsyncResult* <xref:System.Transactions.CommittableTransaction> метода <xref:System.IAsyncResult> обратного вызова, так как класс реализует класс.  
  
 В следующем примере показано, как выполнить асинхронную фиксацию.  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Реализация неявной транзакции с использованием области транзакции](implementing-an-implicit-transaction-using-transaction-scope.md)
- [Обработка транзакций](index.md)
