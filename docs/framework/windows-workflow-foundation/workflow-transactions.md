---
title: Транзакции рабочих процессов
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: cb2a72bb24640d214170c52b8b3bf0a328d3f775
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714623"
---
# <a name="workflow-transactions"></a>Транзакции рабочих процессов

[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет поддержку участия в транзакциях <xref:System.Transactions> с использованием <xref:System.Activities.Statements.TransactionScope> для определения области для единицы работы транзакции. В то время как <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> должна завершаться явно, действие <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> неявно вызывает завершение транзакции в случае успешного завершения. Все действия, содержащиеся в <xref:System.Activities.Statements.TransactionScope.Body%2A> действия <xref:System.Activities.Statements.TransactionScope>, принимают участие в транзакции. WF способен передавать транзакции в рабочий процесс при помощи действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Аналогично действию <xref:System.Activities.Statements.TransactionScope>, любое действие, содержащееся в <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>, участвует в транзакции. WF обеспечивает работу действий, зависимых от <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>, как с <xref:System.Activities.Statements.TransactionScope>, так и с <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Если системные действия не удовлетворяют всем существующим требованиям, можно создать пользовательские действия с помощью <xref:System.Activities.RuntimeTransactionHandle>, чтобы реализовать расширенные схемы управления потоком и транзакциями.  
  
В следующем примере создан рабочий процесс, состоящий из <xref:System.Activities.Statements.Sequence> действие, которое содержит дочерние действия, в том числе <xref:System.Activities.Statements.TransactionScope> действия. Действия <xref:System.Activities.Statements.TransactionScope.Body%2A> из <xref:System.Activities.Statements.TransactionScope> выполняются в рамках транзакции, инициализированной действием <xref:System.Activities.Statements.TransactionScope>.  
  
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
  
Дополнительные сведения см. в разделе об использовании <xref:System.ServiceModel.Activities.TransactedReceiveScope>, см. в разделе [транзакций, передаваемых в действие и из служб рабочих процессов](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Activities.Statements.TransactionScope>
- <xref:System.Transactions.TransactionScope>
- <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
