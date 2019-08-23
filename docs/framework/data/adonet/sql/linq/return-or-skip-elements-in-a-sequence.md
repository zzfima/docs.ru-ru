---
title: Возврат или пропуск элементов последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 75cb5ea166c36de5c0921fbbd830021719497cda
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963864"
---
# <a name="return-or-skip-elements-in-a-sequence"></a><span data-ttu-id="4692d-102">Возврат или пропуск элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="4692d-102">Return Or Skip Elements in a Sequence</span></span>
<span data-ttu-id="4692d-103">Для возвращения заданного числа элементов последовательности и пропуска оставшихся используется оператор <xref:System.Linq.Queryable.Take%2A>.</span><span class="sxs-lookup"><span data-stu-id="4692d-103">Use the <xref:System.Linq.Queryable.Take%2A> operator to return a given number of elements in a sequence and then skip over the remainder.</span></span>  
  
 <span data-ttu-id="4692d-104">Для пропуска заданного числа элементов последовательности и возвращения оставшихся используется оператор <xref:System.Linq.Queryable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="4692d-104">Use the <xref:System.Linq.Queryable.Skip%2A> operator to skip over a given number of elements in a sequence and then return the remainder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4692d-105">На методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> накладываются некоторые ограничения при их использовании в запросах для SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="4692d-105"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="4692d-106">Дополнительные сведения см. в записи "пропуск и получение исключений в SQL Server 2000" раздела [Устранение неполадок](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="4692d-106">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4692d-107">Преобразует <xref:System.Linq.Queryable.Skip%2A> с помощью вложенного запроса с предложением SQL `NOT EXISTS` .</span><span class="sxs-lookup"><span data-stu-id="4692d-107">translates <xref:System.Linq.Queryable.Skip%2A> by using a subquery with the SQL `NOT EXISTS` clause.</span></span> <span data-ttu-id="4692d-108">Это преобразование имеет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="4692d-108">This translation has the following limitations:</span></span>  
  
- <span data-ttu-id="4692d-109">Необходимо задать значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="4692d-109">The argument must be a set.</span></span> <span data-ttu-id="4692d-110">Не поддерживаются множественные наборы, даже упорядоченные.</span><span class="sxs-lookup"><span data-stu-id="4692d-110">Multisets are not supported, even if ordered.</span></span>  
  
- <span data-ttu-id="4692d-111">Созданный запрос может быть сложнее, чем запрос, созданный для основного запроса, к которому применен <xref:System.Linq.Queryable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="4692d-111">The generated query can be much more complex than the query generated for the base query on which <xref:System.Linq.Queryable.Skip%2A> is applied.</span></span> <span data-ttu-id="4692d-112">Это может стать причиной снижения производительности или даже привести к превышению времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="4692d-112">This complexity can cause decrease in performance or even a time-out.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4692d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4692d-113">Example</span></span>  
 <span data-ttu-id="4692d-114">В следующем примере для выбора первых пяти принятых на работу `Take` используется метод `Employees`.</span><span class="sxs-lookup"><span data-stu-id="4692d-114">The following example uses `Take` to select the first five `Employees` hired.</span></span> <span data-ttu-id="4692d-115">Обратите внимание, что коллекция сначала сортируется по `HireDate`.</span><span class="sxs-lookup"><span data-stu-id="4692d-115">Note that the collection is first sorted by `HireDate`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="4692d-116">Пример</span><span class="sxs-lookup"><span data-stu-id="4692d-116">Example</span></span>  
 <span data-ttu-id="4692d-117">В следующем примере для выбора всех <xref:System.Linq.Queryable.Skip%2A>, за исключением 10 самых дорогих, используется метод `Products`.</span><span class="sxs-lookup"><span data-stu-id="4692d-117">The following example uses <xref:System.Linq.Queryable.Skip%2A> to select all except the 10 most expensive `Products`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="4692d-118">Пример</span><span class="sxs-lookup"><span data-stu-id="4692d-118">Example</span></span>  
 <span data-ttu-id="4692d-119">В следующем примере для пропуска первых 50 и возвращения следующих за ними 10 записей методы <xref:System.Linq.Queryable.Skip%2A> и <xref:System.Linq.Queryable.Take%2A> объединяются.</span><span class="sxs-lookup"><span data-stu-id="4692d-119">The following example combines the <xref:System.Linq.Queryable.Skip%2A> and <xref:System.Linq.Queryable.Take%2A> methods to skip the first 50 records and then return the next 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 <span data-ttu-id="4692d-120">Методы <xref:System.Linq.Queryable.Take%2A> и <xref:System.Linq.Queryable.Skip%2A> правильно определяются только для упорядоченных наборов.</span><span class="sxs-lookup"><span data-stu-id="4692d-120"><xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> operations are well defined only against ordered sets.</span></span> <span data-ttu-id="4692d-121">Семантика для неупорядоченных наборов или множественных наборов не определена.</span><span class="sxs-lookup"><span data-stu-id="4692d-121">The semantics for unordered sets or multisets is undefined.</span></span>  
  
 <span data-ttu-id="4692d-122">Из-за ограничений, накладываемых на упорядочение в SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предпринимает попытку переместить упорядочение аргументов оператора <xref:System.Linq.Queryable.Take%2A> или <xref:System.Linq.Queryable.Skip%2A>в результат оператора.</span><span class="sxs-lookup"><span data-stu-id="4692d-122">Because of the limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of the <xref:System.Linq.Queryable.Take%2A> or <xref:System.Linq.Queryable.Skip%2A> operator to the result of the operator.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4692d-123">Преобразование отличается для SQL Server 2000 и SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="4692d-123">Translation is different for SQL Server 2000 and SQL Server 2005.</span></span> <span data-ttu-id="4692d-124">Если вы планируете использовать <xref:System.Linq.Queryable.Skip%2A> с запросом любой сложности, используйте SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="4692d-124">If you plan to use <xref:System.Linq.Queryable.Skip%2A> with a query of any complexity, use SQL Server 2005.</span></span>  
  
 <span data-ttu-id="4692d-125">Рассмотрим следующий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запрос для SQL Server 2000:</span><span class="sxs-lookup"><span data-stu-id="4692d-125">Consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query for SQL Server 2000:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4692d-126">перемещает упорядочение в конец кода SQL, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="4692d-126">moves the ordering to the end in the SQL code, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="4692d-127">При связывании методов <xref:System.Linq.Queryable.Take%2A> и <xref:System.Linq.Queryable.Skip%2A> друг с другом все указанные операции упорядочения должны быть согласованы.</span><span class="sxs-lookup"><span data-stu-id="4692d-127">When <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are chained together, all the specified ordering must be consistent.</span></span> <span data-ttu-id="4692d-128">В противном случае результаты не определены.</span><span class="sxs-lookup"><span data-stu-id="4692d-128">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="4692d-129">Методы <xref:System.Linq.Queryable.Take%2A> и <xref:System.Linq.Queryable.Skip%2A> правильно определяются для неотрицательных постоянных целочисленных аргументов, соответствующих спецификации SQL.</span><span class="sxs-lookup"><span data-stu-id="4692d-129">For non-negative, constant integral arguments based on the SQL specification, both <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are well-defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4692d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4692d-130">See also</span></span>

- [<span data-ttu-id="4692d-131">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="4692d-131">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="4692d-132">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="4692d-132">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
