---
title: "Транзакции рабочих процессов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Транзакции рабочих процессов
[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет поддержку участия в транзакциях <xref:System.Transactions> с использованием <xref:System.Activities.Statements.TransactionScope> для определения области для единицы работы транзакции.В то время как <xref:System.Transactions.TransactionScope?displayProperty=fullName> должна завершаться явно, действие <xref:System.Activities.Statements.TransactionScope?displayProperty=fullName> неявно вызывает завершение транзакции в случае успешного завершения.Все действия, содержащиеся в элементе <xref:System.Activities.Statements.TransactionScope.Body%2A> действия <xref:System.Activities.Statements.TransactionScope>, участвуют в транзакции.WF способен передавать транзакции в рабочий процесс при помощи действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Аналогично действию <xref:System.Activities.Statements.TransactionScope>, любое действие, содержащееся в <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>, участвует в транзакции.WF обеспечивает работу действий, зависимых от <xref:System.Transactions.Transaction.Current%2A?displayProperty=fullName>, как с <xref:System.Activities.Statements.TransactionScope>, так и с <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Если системные действия не удовлетворяют всем существующим требованиям, можно создать пользовательские действия с помощью <xref:System.Activities.RuntimeTransactionHandle>, чтобы реализовать расширенные схемы управления потоком и транзакциями.  
  
 В следующем примере из образца [Простой класс TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) создается рабочий процесс, содержащий действие <xref:System.Activities.Statements.Sequence>, которое включает в себя дочерние действия, в том числе действие <xref:System.Activities.Statements.TransactionScope>.Действия <xref:System.Activities.Statements.TransactionScope.Body%2A> из <xref:System.Activities.Statements.TransactionScope> выполняются в рамках транзакции, инициализированной действием <xref:System.Activities.Statements.TransactionScope>.  
  
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
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] базовые образцы [Транзакции](../../../docs/framework/windows-workflow-foundation/samples/basic-transactions.md) и основанные на сценариях образцы [Транзакции](../../../docs/framework/windows-workflow-foundation/samples/transactions.md).[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] об использовании <xref:System.ServiceModel.Activities.TransactedReceiveScope> см. в разделе [Направление транзакций в службы рабочего процесса и из них](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## См. также  
 <xref:System.Activities.Statements.TransactionScope>   
 <xref:System.Transactions.TransactionScope>   
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=fullName>