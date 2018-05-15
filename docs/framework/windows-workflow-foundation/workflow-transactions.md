---
title: Транзакции рабочих процессов
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 2bb5f6498b365f3b773eea9a5adce1ec1158a289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="workflow-transactions"></a><span data-ttu-id="ff4b6-102">Транзакции рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ff4b6-102">Workflow Transactions</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="ff4b6-103"> предоставляет поддержку участия в транзакциях <xref:System.Transactions> с использованием <xref:System.Activities.Statements.TransactionScope> для определения области для единицы работы транзакции.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-103"> provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="ff4b6-104">В то время как <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> должна завершаться явно, действие <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> неявно вызывает завершение транзакции в случае успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="ff4b6-105">Все действия, содержащиеся в <xref:System.Activities.Statements.TransactionScope.Body%2A> действия <xref:System.Activities.Statements.TransactionScope>, принимают участие в транзакции.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="ff4b6-106">WF способен передавать транзакции в рабочий процесс при помощи действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="ff4b6-107">Аналогично действию <xref:System.Activities.Statements.TransactionScope>, любое действие, содержащееся в <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>, участвует в транзакции.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="ff4b6-108">WF обеспечивает работу действий, зависимых от <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>, как с <xref:System.Activities.Statements.TransactionScope>, так и с <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="ff4b6-109">Если системные действия не удовлетворяют всем существующим требованиям, можно создать пользовательские действия с помощью <xref:System.Activities.RuntimeTransactionHandle>, чтобы реализовать расширенные схемы управления потоком и транзакциями.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
 <span data-ttu-id="ff4b6-110">В следующем примере берется из [простой класс TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) примера создается рабочий процесс, состоящий из <xref:System.Activities.Statements.Sequence> действием, которое содержит дочерние действия, в том числе <xref:System.Activities.Statements.TransactionScope> действия.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-110">In the following example, taken from the [Basic TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) sample, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="ff4b6-111">Действия <xref:System.Activities.Statements.TransactionScope.Body%2A> из <xref:System.Activities.Statements.TransactionScope> выполняются в рамках транзакции, инициализированной действием <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
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
  
 <span data-ttu-id="ff4b6-112">Дополнительные сведения см. в разделе Основные [транзакции](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) примеры и сценарии на основе [транзакции](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) образцов.</span><span class="sxs-lookup"><span data-stu-id="ff4b6-112">For more information, see the basic [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples, and the scenario based [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples.</span></span> <span data-ttu-id="ff4b6-113">Дополнительные сведения см. в разделе об использовании <xref:System.ServiceModel.Activities.TransactedReceiveScope>, в разделе [поток транзакций в службы рабочего процесса и из](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff4b6-113">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4b6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ff4b6-114">See Also</span></span>  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
