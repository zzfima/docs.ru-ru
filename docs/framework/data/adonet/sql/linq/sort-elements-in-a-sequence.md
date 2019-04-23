---
title: Сортировка элементов последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 33473eadefabc2bcbbb552d225d021eae4bed0bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169017"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="293f1-102">Сортировка элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="293f1-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="293f1-103">Для сортировки последовательности по одному или нескольким ключам используется оператор <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="293f1-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="293f1-104">предназначен для поддержки упорядочения по простым примитивным типам, например `string`, `int`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="293f1-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="293f1-105">В этой технологии не поддерживается упорядочение для сложных многозначных классов, таких как анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="293f1-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="293f1-106">В ней также не поддерживаются типы данных `byte`.</span><span class="sxs-lookup"><span data-stu-id="293f1-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="293f1-107">Пример</span><span class="sxs-lookup"><span data-stu-id="293f1-107">Example</span></span>  
 <span data-ttu-id="293f1-108">В следующем примере выполняется сортировка сотрудников (`Employees`) по дате приема на работу.</span><span class="sxs-lookup"><span data-stu-id="293f1-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="293f1-109">Пример</span><span class="sxs-lookup"><span data-stu-id="293f1-109">Example</span></span>  
 <span data-ttu-id="293f1-110">В следующем примере для сортировки заказов (`where`), поставленных в Лондон (`Orders`), по типу перевозки используется предложение `London`.</span><span class="sxs-lookup"><span data-stu-id="293f1-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="293f1-111">Пример</span><span class="sxs-lookup"><span data-stu-id="293f1-111">Example</span></span>  
 <span data-ttu-id="293f1-112">В следующем примере выполняется сортировка продуктов (`Products`) по цене единицы товара по убыванию.</span><span class="sxs-lookup"><span data-stu-id="293f1-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="293f1-113">Пример</span><span class="sxs-lookup"><span data-stu-id="293f1-113">Example</span></span>  
 <span data-ttu-id="293f1-114">В следующем примере для сортировки клиентов (`OrderBy`) по городу, а затем по контактному лицу используется составной оператор `Customers`.</span><span class="sxs-lookup"><span data-stu-id="293f1-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="293f1-115">Пример</span><span class="sxs-lookup"><span data-stu-id="293f1-115">Example</span></span>  
 <span data-ttu-id="293f1-116">В следующем примере выполняется сортировка заказов от сотрудника `EmployeeID 1` по стране доставки, а затем по типу перевозки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="293f1-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="293f1-117">Пример</span><span class="sxs-lookup"><span data-stu-id="293f1-117">Example</span></span>  
 <span data-ttu-id="293f1-118">В следующем примере объединяются операторы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> и <xref:System.Linq.Enumerable.GroupBy%2A>, чтобы найти продукты (`Products`) с максимальной ценой за единицу товара в каждой категории, а затем выполнить сортировку полученной группы по коду категории.</span><span class="sxs-lookup"><span data-stu-id="293f1-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="293f1-119">Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="293f1-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="293f1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="293f1-120">See also</span></span>

- [<span data-ttu-id="293f1-121">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="293f1-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="293f1-122">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="293f1-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
