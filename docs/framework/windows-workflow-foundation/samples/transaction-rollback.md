---
title: Откат транзакции
ms.date: 03/30/2017
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
ms.openlocfilehash: 15333b159625f07449b0a93634a1a9a854614a57
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517161"
---
# <a name="transaction-rollback"></a>Откат транзакции
Этот образец показывает, как создавать пользовательское действие <xref:System.Activities.NativeActivity>, которое обращается к внешнему дескриптору <xref:System.Activities.RuntimeTransactionHandle> для получения внешней транзакции и выполнения явного ее отката.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В рабочем процессе транзакция будет автоматически завершена в момент завершения самой внешней транзакции <xref:System.Activities.Statements.TransactionScope> или <xref:System.ServiceModel.Activities.TransactedReceiveScope>.  Когда необработанное исключение распространяется через границу области, осуществляется явный откат транзакции. Однако могут встречаться случаи, когда явный откат транзакции имеет смысл выполнять, не вызывая исключение. В этом случае можно использовать пользовательское действие отката (как в этом образце), чтобы явным образом прервать внешнюю транзакцию и выдать дополнительную причину исключения.  
  
 Действие `RollbackActivity` представляет собой действие <xref:System.Activities.NativeActivity>, поскольку оно требует доступа к свойствам исключения для получения внешнего дескриптора <xref:System.Activities.RuntimeTransactionHandle>. В методе `Execute` действие получает дескриптор <xref:System.Activities.RuntimeTransactionHandle> и проверяет его значение. Значение `null` означает, что действие было использовано без внешней транзакции времени выполнения. Затем происходит получение транзакции с такой же проверкой значения `null`. Внешний дескриптор <xref:System.Activities.RuntimeTransactionHandle> можно получить, вообще не запуская транзакцию времени выполнения. Затем происходит прерывание транзакции посредством вызова метода <xref:System.Transactions.Transaction.Rollback%2A> и указания либо пользовательского, либо универсального исключения, устанавливающего, что данное действие совершило откат транзакции.  
  
 Демонстрационный рабочий процесс состоит из класса <xref:System.Activities.Statements.TransactionScope>, тело которого выводит на экран консоли состояние транзакции до и после выполнения `RollbackActivity`. Обратите внимание, что <xref:System.Activities.Statements.TransactionScope> будет выполняться вплоть до завершения, даже если был совершен откат транзакции, при этом рабочий процесс не будет прерываться до завершения тела запроса. Рабочий процесс будет прерван в том случае, если значение свойства <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> примет значение по умолчанию `true`.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Загрузите решение TransactionRollback.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Нажмите CTRL+F5, чтобы запустить приложение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## <a name="see-also"></a>См. также  
 [Транзакции](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)
