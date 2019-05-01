---
title: Практическое руководство. Как обрабатывать составные ключи в запросах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 2621ab4db207d1b868fbe3778c30c744201b0506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033817"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="298db-102">Практическое руководство. Как обрабатывать составные ключи в запросах</span><span class="sxs-lookup"><span data-stu-id="298db-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="298db-103">Некоторые операторы могут принимать только один аргумент.</span><span class="sxs-lookup"><span data-stu-id="298db-103">Some operators can take only one argument.</span></span> <span data-ttu-id="298db-104">Если аргумент должен содержать несколько столбцов базы данных, необходимо создать анонимный тип для представления комбинации столбцов.</span><span class="sxs-lookup"><span data-stu-id="298db-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="298db-105">Пример</span><span class="sxs-lookup"><span data-stu-id="298db-105">Example</span></span>  
 <span data-ttu-id="298db-106">В следующем примере показан запрос, который вызывает оператор `GroupBy`, принимающий только один аргумент `key`.</span><span class="sxs-lookup"><span data-stu-id="298db-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="298db-107">Пример</span><span class="sxs-lookup"><span data-stu-id="298db-107">Example</span></span>  
 <span data-ttu-id="298db-108">Та же ситуация возникает в случае соединений, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="298db-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="298db-109">См. также</span><span class="sxs-lookup"><span data-stu-id="298db-109">See also</span></span>

- [<span data-ttu-id="298db-110">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="298db-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
