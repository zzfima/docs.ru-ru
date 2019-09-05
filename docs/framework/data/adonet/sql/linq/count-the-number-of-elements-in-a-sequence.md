---
title: Подсчет количества элементов в последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 74e24aeb64b0097cba3975e76475034e6bb9544d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247706"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="d1c64-102">Подсчет количества элементов в последовательности</span><span class="sxs-lookup"><span data-stu-id="d1c64-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="d1c64-103">Для подсчета числа элементов в последовательности используется оператор <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1c64-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="d1c64-104">При выполнении данного запроса в учебной базе данных "Northwind" возвращается значение `91`.</span><span class="sxs-lookup"><span data-stu-id="d1c64-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1c64-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d1c64-105">Example</span></span>  
 <span data-ttu-id="d1c64-106">В следующем примере подсчитывается количество клиентов (`Customers`) в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d1c64-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="d1c64-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d1c64-107">Example</span></span>  
 <span data-ttu-id="d1c64-108">В следующем примере подсчитывается количество продуктов в базе данных, еще не снятых с производства.</span><span class="sxs-lookup"><span data-stu-id="d1c64-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="d1c64-109">При выполнении данного примера в учебной базе данных "Northwind" возвращается значение `69`.</span><span class="sxs-lookup"><span data-stu-id="d1c64-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d1c64-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d1c64-110">See also</span></span>

- [<span data-ttu-id="d1c64-111">Статистические запросы</span><span class="sxs-lookup"><span data-stu-id="d1c64-111">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="d1c64-112">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="d1c64-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
