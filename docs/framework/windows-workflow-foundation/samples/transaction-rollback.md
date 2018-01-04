---
title: "Откат транзакции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 85ae459a8e79beba9ecffb16476b37468aeb632e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-rollback"></a><span data-ttu-id="f5157-102">Откат транзакции</span><span class="sxs-lookup"><span data-stu-id="f5157-102">Transaction Rollback</span></span>
<span data-ttu-id="f5157-103">Этот образец показывает, как создавать пользовательское действие <xref:System.Activities.NativeActivity>, которое обращается к внешнему дескриптору <xref:System.Activities.RuntimeTransactionHandle> для получения внешней транзакции и выполнения явного ее отката.</span><span class="sxs-lookup"><span data-stu-id="f5157-103">This sample shows how to create a custom <xref:System.Activities.NativeActivity> that accesses the ambient <xref:System.Activities.RuntimeTransactionHandle> to get the ambient transaction and explicitly roll it back.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f5157-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="f5157-104">Sample Details</span></span>  
 <span data-ttu-id="f5157-105">В рабочем процессе транзакция будет автоматически завершена в момент завершения самой внешней транзакции <xref:System.Activities.Statements.TransactionScope> или <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="f5157-105">In workflow, a transaction is automatically completed when the outermost <xref:System.Activities.Statements.TransactionScope> or <xref:System.ServiceModel.Activities.TransactedReceiveScope> completes.</span></span>  <span data-ttu-id="f5157-106">Когда необработанное исключение распространяется через границу области, осуществляется явный откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="f5157-106">A transaction implicitly rolls back when an unhandled exception propagates across the scope boundary.</span></span> <span data-ttu-id="f5157-107">Однако могут встречаться случаи, когда явный откат транзакции имеет смысл выполнять, не вызывая исключение.</span><span class="sxs-lookup"><span data-stu-id="f5157-107">However, there may be times when it makes sense to explicitly roll back a transaction without having to throw an exception.</span></span> <span data-ttu-id="f5157-108">В этом случае можно использовать пользовательское действие отката (как в этом образце), чтобы явным образом прервать внешнюю транзакцию и выдать дополнительную причину исключения.</span><span class="sxs-lookup"><span data-stu-id="f5157-108">In this case, you can use the custom rollback activity like the one in this sample to explicitly abort the ambient transaction and provide an optional exception reason.</span></span>  
  
 <span data-ttu-id="f5157-109">Действие `RollbackActivity` представляет собой действие <xref:System.Activities.NativeActivity>, поскольку оно требует доступа к свойствам исключения для получения внешнего дескриптора <xref:System.Activities.RuntimeTransactionHandle>.</span><span class="sxs-lookup"><span data-stu-id="f5157-109">The `RollbackActivity` is a <xref:System.Activities.NativeActivity> as it requires access to the execution properties to get the ambient <xref:System.Activities.RuntimeTransactionHandle>.</span></span> <span data-ttu-id="f5157-110">В методе `Execute` действие получает дескриптор <xref:System.Activities.RuntimeTransactionHandle> и проверяет его значение. Значение `null` означает, что действие было использовано без внешней транзакции времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f5157-110">In the `Execute` method, it obtains the <xref:System.Activities.RuntimeTransactionHandle> and checks whether it is `null`, which indicates that the activity was used without an ambient run-time transaction.</span></span> <span data-ttu-id="f5157-111">Затем происходит получение транзакции с такой же проверкой значения `null`.</span><span class="sxs-lookup"><span data-stu-id="f5157-111">It then obtains the transaction, again checking whether `null` is present.</span></span> <span data-ttu-id="f5157-112">Внешний дескриптор <xref:System.Activities.RuntimeTransactionHandle> можно получить, вообще не запуская транзакцию времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f5157-112">It is possible to have an ambient <xref:System.Activities.RuntimeTransactionHandle> without ever initializing a run-time transaction.</span></span> <span data-ttu-id="f5157-113">Затем происходит прерывание транзакции посредством вызова метода <xref:System.Transactions.Transaction.Rollback%2A> и указания либо пользовательского, либо универсального исключения, устанавливающего, что данное действие совершило откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="f5157-113">Finally it aborts the transaction by calling <xref:System.Transactions.Transaction.Rollback%2A> and specifying either a user-provided exception or a generic exception that states that the activity rolled back the transaction.</span></span>  
  
 <span data-ttu-id="f5157-114">Демонстрационный рабочий процесс состоит из класса <xref:System.Activities.Statements.TransactionScope>, тело которого выводит на экран консоли состояние транзакции до и после выполнения `RollbackActivity`.</span><span class="sxs-lookup"><span data-stu-id="f5157-114">The demonstration workflow consists of a <xref:System.Activities.Statements.TransactionScope> whose body prints the transaction status before and after the `RollbackActivity` executes.</span></span> <span data-ttu-id="f5157-115">Обратите внимание, что <xref:System.Activities.Statements.TransactionScope> будет выполняться вплоть до завершения, даже если был совершен откат транзакции, при этом рабочий процесс не будет прерываться до завершения тела запроса.</span><span class="sxs-lookup"><span data-stu-id="f5157-115">Note that even though the transaction has been rolled back, the <xref:System.Activities.Statements.TransactionScope> executes to completion and does not abort the workflow until the body completes.</span></span> <span data-ttu-id="f5157-116">Рабочий процесс будет прерван в том случае, если значение свойства <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> примет значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="f5157-116">The workflow is aborted because the <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> property defaults to `true`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f5157-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="f5157-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="f5157-118">Загрузите решение TransactionRollback.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5157-118">Load the TransactionRollback.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f5157-119">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="f5157-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="f5157-120">Нажмите CTRL+F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="f5157-120">Press CTRL+F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5157-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5157-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5157-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f5157-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f5157-123">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5157-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5157-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5157-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## <a name="see-also"></a><span data-ttu-id="f5157-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f5157-125">See Also</span></span>  
 [<span data-ttu-id="f5157-126">Транзакции</span><span class="sxs-lookup"><span data-stu-id="f5157-126">Transactions</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)
