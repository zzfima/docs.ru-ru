---
title: Практическое руководство. Обработка составных ключей в запросах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 26c281445b84d3b3f85980de6ae4076411bb4fba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354244"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="6413a-102">Практическое руководство. Обработка составных ключей в запросах</span><span class="sxs-lookup"><span data-stu-id="6413a-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="6413a-103">Некоторые операторы могут принимать только один аргумент.</span><span class="sxs-lookup"><span data-stu-id="6413a-103">Some operators can take only one argument.</span></span> <span data-ttu-id="6413a-104">Если аргумент должен содержать несколько столбцов базы данных, необходимо создать анонимный тип для представления комбинации столбцов.</span><span class="sxs-lookup"><span data-stu-id="6413a-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6413a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6413a-105">Example</span></span>  
 <span data-ttu-id="6413a-106">В следующем примере показан запрос, который вызывает оператор `GroupBy`, принимающий только один аргумент `key`.</span><span class="sxs-lookup"><span data-stu-id="6413a-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="6413a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6413a-107">Example</span></span>  
 <span data-ttu-id="6413a-108">Та же ситуация возникает в случае соединений, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6413a-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6413a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="6413a-109">See Also</span></span>  
 [<span data-ttu-id="6413a-110">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="6413a-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
