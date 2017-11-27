---
title: "Проверка соответствия условию какого-либо или всех элементов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0dda546c0d8cd073a5d11bdf22805310e3f4f40a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="a93cd-102">Проверка соответствия условию какого-либо или всех элементов</span><span class="sxs-lookup"><span data-stu-id="a93cd-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="a93cd-103">Оператор <xref:System.Linq.Enumerable.All%2A> возвращает значение `true`, если все элементы в последовательности удовлетворяют указанному условию.</span><span class="sxs-lookup"><span data-stu-id="a93cd-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="a93cd-104">Оператор <xref:System.Linq.Queryable.Any%2A> возвращает значение `true`, если какой-либо элемент в коллекции удовлетворяет указанному условию.</span><span class="sxs-lookup"><span data-stu-id="a93cd-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a93cd-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a93cd-105">Example</span></span>  
 <span data-ttu-id="a93cd-106">В следующем примере возвращается последовательность клиентов, сделавших хотя бы один заказ.</span><span class="sxs-lookup"><span data-stu-id="a93cd-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="a93cd-107">`Where` / `where` Предложение `true` Если данного `Customer` должен содержать `Order`.</span><span class="sxs-lookup"><span data-stu-id="a93cd-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="a93cd-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a93cd-108">Example</span></span>  
 <span data-ttu-id="a93cd-109">Следующий код Visual Basic определяет список клиентов, не оформивших заказы, и гарантирует наличие контактного имени для каждого клиента в этом списке.</span><span class="sxs-lookup"><span data-stu-id="a93cd-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="a93cd-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a93cd-110">Example</span></span>  
 <span data-ttu-id="a93cd-111">В следующем примере C# возвращается последовательность клиентов, `ShipCity` в заказах которых начинается с буквы "С".</span><span class="sxs-lookup"><span data-stu-id="a93cd-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="a93cd-112">Кроме того, в полученном результате будут указаны клиенты, не сделавшие ни одного заказа.</span><span class="sxs-lookup"><span data-stu-id="a93cd-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="a93cd-113">(Для пустой последовательности оператор <xref:System.Linq.Queryable.All%2A> намеренно возвращает значение `true`.) Клиенты, не имеющие заказов, удаляются из вывода на консоли с помощью оператора `Count`.</span><span class="sxs-lookup"><span data-stu-id="a93cd-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="a93cd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a93cd-114">See Also</span></span>  
 [<span data-ttu-id="a93cd-115">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="a93cd-115">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
