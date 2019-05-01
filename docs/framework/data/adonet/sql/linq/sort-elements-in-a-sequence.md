---
title: Сортировка элементов последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 33473eadefabc2bcbbb552d225d021eae4bed0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033388"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="dc860-102">Сортировка элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="dc860-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="dc860-103">Для сортировки последовательности по одному или нескольким ключам используется оператор <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc860-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="dc860-104">предназначен для поддержки упорядочения по простым примитивным типам, например `string`, `int`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="dc860-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="dc860-105">В этой технологии не поддерживается упорядочение для сложных многозначных классов, таких как анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="dc860-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="dc860-106">В ней также не поддерживаются типы данных `byte`.</span><span class="sxs-lookup"><span data-stu-id="dc860-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc860-107">Пример</span><span class="sxs-lookup"><span data-stu-id="dc860-107">Example</span></span>  
 <span data-ttu-id="dc860-108">В следующем примере выполняется сортировка сотрудников (`Employees`) по дате приема на работу.</span><span class="sxs-lookup"><span data-stu-id="dc860-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="dc860-109">Пример</span><span class="sxs-lookup"><span data-stu-id="dc860-109">Example</span></span>  
 <span data-ttu-id="dc860-110">В следующем примере для сортировки заказов (`where`), поставленных в Лондон (`Orders`), по типу перевозки используется предложение `London`.</span><span class="sxs-lookup"><span data-stu-id="dc860-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="dc860-111">Пример</span><span class="sxs-lookup"><span data-stu-id="dc860-111">Example</span></span>  
 <span data-ttu-id="dc860-112">В следующем примере выполняется сортировка продуктов (`Products`) по цене единицы товара по убыванию.</span><span class="sxs-lookup"><span data-stu-id="dc860-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="dc860-113">Пример</span><span class="sxs-lookup"><span data-stu-id="dc860-113">Example</span></span>  
 <span data-ttu-id="dc860-114">В следующем примере для сортировки клиентов (`OrderBy`) по городу, а затем по контактному лицу используется составной оператор `Customers`.</span><span class="sxs-lookup"><span data-stu-id="dc860-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="dc860-115">Пример</span><span class="sxs-lookup"><span data-stu-id="dc860-115">Example</span></span>  
 <span data-ttu-id="dc860-116">В следующем примере выполняется сортировка заказов от сотрудника `EmployeeID 1` по стране доставки, а затем по типу перевозки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="dc860-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="dc860-117">Пример</span><span class="sxs-lookup"><span data-stu-id="dc860-117">Example</span></span>  
 <span data-ttu-id="dc860-118">В следующем примере объединяются операторы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> и <xref:System.Linq.Enumerable.GroupBy%2A>, чтобы найти продукты (`Products`) с максимальной ценой за единицу товара в каждой категории, а затем выполнить сортировку полученной группы по коду категории.</span><span class="sxs-lookup"><span data-stu-id="dc860-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="dc860-119">Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc860-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="dc860-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dc860-120">See also</span></span>

- [<span data-ttu-id="dc860-121">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="dc860-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="dc860-122">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="dc860-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
