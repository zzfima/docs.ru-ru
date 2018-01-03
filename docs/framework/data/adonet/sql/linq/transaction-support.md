---
title: "Поддержка транзакций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 79cd52f137347ec24e7cc9a646d0306d95fe53d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-support"></a><span data-ttu-id="a5bf0-102">Поддержка транзакций</span><span class="sxs-lookup"><span data-stu-id="a5bf0-102">Transaction Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a5bf0-103">поддерживает три различные модели транзакций.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-103"> supports three distinct transaction models.</span></span> <span data-ttu-id="a5bf0-104">Далее представлен список этих моделей в порядке выполненных проверок.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-104">The following lists these models in the order of checks performed.</span></span>  
  
## <a name="explicit-local-transaction"></a><span data-ttu-id="a5bf0-105">Явные локальные транзакции</span><span class="sxs-lookup"><span data-stu-id="a5bf0-105">Explicit Local Transaction</span></span>  
 <span data-ttu-id="a5bf0-106">При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, если свойству <xref:System.Data.Linq.DataContext.Transaction%2A> задана транзакция (`IDbTransaction`), вызов <xref:System.Data.Linq.DataContext.SubmitChanges%2A> выполняется в контексте этой же транзакции.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-106">When <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called, if the <xref:System.Data.Linq.DataContext.Transaction%2A> property is set to a (`IDbTransaction`) transaction, the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> call is executed in the context of the same transaction.</span></span>  
  
 <span data-ttu-id="a5bf0-107">Вашей обязанностью является выполнение фиксации или отката транзакции после ее успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-107">It is your responsibility to commit or rollback the transaction after successful execution of the transaction.</span></span> <span data-ttu-id="a5bf0-108">Подключение, соответствующее транзакции, должно совпадать с подключением, используемым для создания <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-108">The connection corresponding to the transaction must match the connection used for constructing the <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="a5bf0-109">При использовании разных подключений создается исключение.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-109">An exception is thrown if a different connection is used.</span></span>  
  
## <a name="explicit-distributable-transaction"></a><span data-ttu-id="a5bf0-110">Явные распределяемые транзакции</span><span class="sxs-lookup"><span data-stu-id="a5bf0-110">Explicit Distributable Transaction</span></span>  
 <span data-ttu-id="a5bf0-111">Можно вызвать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API-интерфейсы (включая, но не ограничиваясь <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) в области действия активного <xref:System.Transactions.Transaction>.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-111">You can call [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (including but not limited to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) in the scope of an active <xref:System.Transactions.Transaction>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a5bf0-112">обнаруживает, что вызов находится в области транзакции и не создает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-112"> detects that the call is in the scope of a transaction and does not create a new transaction.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a5bf0-113">также позволяет избежать в этом случае закрытия соединения.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-113"> also avoids closing the connection in this case.</span></span> <span data-ttu-id="a5bf0-114">В контексте данной транзакции можно осуществить запрос и выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-114">You can perform query and <xref:System.Data.Linq.DataContext.SubmitChanges%2A> executions in the context of such a transaction.</span></span>  
  
## <a name="implicit-transaction"></a><span data-ttu-id="a5bf0-115">Неявные транзакции</span><span class="sxs-lookup"><span data-stu-id="a5bf0-115">Implicit Transaction</span></span>  
 <span data-ttu-id="a5bf0-116">При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проверяет, выполняется ли вызов в области <xref:System.Transactions.Transaction> или если `Transaction` свойство (`IDbTransaction`) имеет значение пользователем локальная транзакция.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-116">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] checks to see whether the call is in the scope of a <xref:System.Transactions.Transaction> or if the `Transaction` property (`IDbTransaction`) is set to a user-started local transaction.</span></span> <span data-ttu-id="a5bf0-117">Если транзакции не [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запускает локальную транзакцию (`IDbTransaction`) и использует ее для выполнения сгенерированных команд SQL.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-117">If it finds neither transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a local transaction (`IDbTransaction`) and uses it to execute the generated SQL commands.</span></span> <span data-ttu-id="a5bf0-118">После успешного выполнения всех команд SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] фиксирует локальную транзакцию и возвращается.</span><span class="sxs-lookup"><span data-stu-id="a5bf0-118">When all SQL commands have been successfully completed, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] commits the local transaction and returns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5bf0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a5bf0-119">See Also</span></span>  
 [<span data-ttu-id="a5bf0-120">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="a5bf0-120">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="a5bf0-121">Практическое руководство. Группировка отправок данных с использованием транзакций</span><span class="sxs-lookup"><span data-stu-id="a5bf0-121">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
