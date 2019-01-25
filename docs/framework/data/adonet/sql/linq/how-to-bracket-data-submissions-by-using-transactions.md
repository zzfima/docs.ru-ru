---
title: Как выполнить объединить в пакеты отправку данных с помощью транзакций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 2cbb50cc8762780849c337b597bbb36631c6ac1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584536"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="56d73-102">Как выполнить объединить в пакеты отправку данных с помощью транзакций</span><span class="sxs-lookup"><span data-stu-id="56d73-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="56d73-103">Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="56d73-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="56d73-104">Дополнительные сведения см. в разделе [поддержки транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="56d73-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56d73-105">Пример</span><span class="sxs-lookup"><span data-stu-id="56d73-105">Example</span></span>  
 <span data-ttu-id="56d73-106">В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="56d73-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="56d73-107">См. также</span><span class="sxs-lookup"><span data-stu-id="56d73-107">See also</span></span>
- [<span data-ttu-id="56d73-108">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="56d73-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="56d73-109">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="56d73-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="56d73-110">Поддержка транзакций</span><span class="sxs-lookup"><span data-stu-id="56d73-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
