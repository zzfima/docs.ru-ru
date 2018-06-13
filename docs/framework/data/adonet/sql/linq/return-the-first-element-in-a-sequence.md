---
title: Возврат первого элемента в последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: fd228b2d7534feca3cff49586ac0d43fbf9bcb1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361352"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="a0fe0-102">Возврат первого элемента в последовательности</span><span class="sxs-lookup"><span data-stu-id="a0fe0-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="a0fe0-103">Для возвращения первого элемента последовательности используется оператор <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="a0fe0-104">Запросы, использующие оператор <xref:System.Linq.Enumerable.First%2A>, выполняются немедленно.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a0fe0-105"> не поддерживает оператор <xref:System.Linq.Enumerable.Last%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-105"> does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0fe0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a0fe0-106">Example</span></span>  
 <span data-ttu-id="a0fe0-107">В следующем примере кода выполняется поиск первого поставщика (`Shipper`) в таблице.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="a0fe0-108">При выполнении данного запроса в учебной базе данных "Northwind" возвращается результат:</span><span class="sxs-lookup"><span data-stu-id="a0fe0-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="a0fe0-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="a0fe0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a0fe0-110">Example</span></span>  
 <span data-ttu-id="a0fe0-111">В следующем примере кода выполняется поиск отдельного клиента (`Customer`), которому присвоен код (`CustomerID`) BONAP.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="a0fe0-112">При выполнении данного запроса в учебной базе данных "Northwind" возвращается результат `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="a0fe0-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="a0fe0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a0fe0-113">See Also</span></span>  
 [<span data-ttu-id="a0fe0-114">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="a0fe0-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="a0fe0-115">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="a0fe0-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
