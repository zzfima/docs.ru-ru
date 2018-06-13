---
title: Практическое руководство. Группировка отправок данных с использованием транзакций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: aa77d364d1ee4efc09386dd7e889914aeb2f3f26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361531"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="a0422-102">Практическое руководство. Группировка отправок данных с использованием транзакций</span><span class="sxs-lookup"><span data-stu-id="a0422-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="a0422-103">Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="a0422-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="a0422-104">Дополнительные сведения см. в разделе [поддержку транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="a0422-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0422-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a0422-105">Example</span></span>  
 <span data-ttu-id="a0422-106">В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="a0422-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a0422-107">См. также</span><span class="sxs-lookup"><span data-stu-id="a0422-107">See Also</span></span>  
 [<span data-ttu-id="a0422-108">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="a0422-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="a0422-109">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="a0422-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="a0422-110">Поддержка транзакций</span><span class="sxs-lookup"><span data-stu-id="a0422-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
