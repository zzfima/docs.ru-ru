---
title: "Транзакции рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 50c720395a8319f4590edb1c495c343d481c73c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="workflow-transactions"></a>Транзакции рабочих процессов
[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет поддержку участия в транзакциях <xref:System.Transactions> с использованием <xref:System.Activities.Statements.TransactionScope> для определения области для единицы работы транзакции. В то время как <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> должна завершаться явно, действие <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> неявно вызывает завершение транзакции в случае успешного завершения. Все действия, содержащиеся в <xref:System.Activities.Statements.TransactionScope.Body%2A> действия <xref:System.Activities.Statements.TransactionScope>, принимают участие в транзакции. WF способен передавать транзакции в рабочий процесс при помощи действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Аналогично действию <xref:System.Activities.Statements.TransactionScope>, любое действие, содержащееся в <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>, участвует в транзакции. WF обеспечивает работу действий, зависимых от <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>, как с <xref:System.Activities.Statements.TransactionScope>, так и с <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Если системные действия не удовлетворяют всем существующим требованиям, можно создать пользовательские действия с помощью <xref:System.Activities.RuntimeTransactionHandle>, чтобы реализовать расширенные схемы управления потоком и транзакциями.  
  
 В следующем примере берется из [простой класс TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) примера создается рабочий процесс, состоящий из <xref:System.Activities.Statements.Sequence> действием, которое содержит дочерние действия, в том числе <xref:System.Activities.Statements.TransactionScope> действия. Действия <xref:System.Activities.Statements.TransactionScope.Body%2A> из <xref:System.Activities.Statements.TransactionScope> выполняются в рамках транзакции, инициализированной действием <xref:System.Activities.Statements.TransactionScope>.  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]базовый [транзакции](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) примеры и сценарии на основе [транзакции](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) образцов. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]об использовании <xref:System.ServiceModel.Activities.TransactedReceiveScope>, в разделе [поток транзакций в службы рабочего процесса и из](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
