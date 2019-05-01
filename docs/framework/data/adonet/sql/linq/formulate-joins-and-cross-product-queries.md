---
title: Практическое руководство. Формулировка запросов-объединений и запросов векторного произведения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: b0037f56947a86627ee9ea84369527aec859a0f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032608"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="87e1a-102">Практическое руководство. Формулировка запросов-объединений и запросов векторного произведения</span><span class="sxs-lookup"><span data-stu-id="87e1a-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="87e1a-103">В следующем примере показано, как объединить результаты из нескольких таблиц.</span><span class="sxs-lookup"><span data-stu-id="87e1a-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87e1a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-104">Example</span></span>  
 <span data-ttu-id="87e1a-105">В следующем примере используется переходы по внешним ключам в `From` предложение в Visual Basic (`from` предложение в C#) для выбора всех заказов для клиентов в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="87e1a-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-106">Example</span></span>  
 <span data-ttu-id="87e1a-107">В следующем примере используется переходы по внешним ключам в `Where` предложение в Visual Basic (`where` предложение в C#) для фильтрации из за `Products` которого `Supplier` находится в США.</span><span class="sxs-lookup"><span data-stu-id="87e1a-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-108">Example</span></span>  
 <span data-ttu-id="87e1a-109">В следующем примере используется переходы по внешним ключам в `From` предложение в Visual Basic (`from` предложение в C#) для фильтрации сотрудников в Сиэтле и обслуживаемыми ими территориями.</span><span class="sxs-lookup"><span data-stu-id="87e1a-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-110">Example</span></span>  
 <span data-ttu-id="87e1a-111">В следующем примере используется переходы по внешним ключам в `Select` предложение в Visual Basic (`select` предложение в C#) для фильтрации пар сотрудников, где один сотрудник сообщает о другом и оба сотрудника находятся с использованием того же `City`.</span><span class="sxs-lookup"><span data-stu-id="87e1a-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-112">Example</span></span>  
 <span data-ttu-id="87e1a-113">В следующем примере Visual Basic выполняет поиск всех клиентов и заказов, гарантирует, что заказы сопоставляются клиентам и гарантирует, что для каждого клиента в этом списке, предоставляется имя контактного лица.</span><span class="sxs-lookup"><span data-stu-id="87e1a-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-114">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-114">Example</span></span>  
 <span data-ttu-id="87e1a-115">В следующем пример явно соединяются две таблицы и проецируются результаты из обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="87e1a-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-116">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-116">Example</span></span>  
 <span data-ttu-id="87e1a-117">В следующем пример явно соединяются три таблицы и проецируются результаты из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="87e1a-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-118">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-118">Example</span></span>  
 <span data-ttu-id="87e1a-119">В следующем примере показано, как реализовать оператор `LEFT OUTER JOIN` с помощью метода `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="87e1a-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="87e1a-120">Если для сотрудника (`DefaultIfEmpty()`) не имеется заказов (`Order`), метод `Employee` возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="87e1a-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-121">Example</span></span>  
 <span data-ttu-id="87e1a-122">В следующем примере проецируется выражение `let`, полученное в результате соединения.</span><span class="sxs-lookup"><span data-stu-id="87e1a-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-123">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-123">Example</span></span>  
 <span data-ttu-id="87e1a-124">В следующем примере показан оператор `join` с композитным ключом.</span><span class="sxs-lookup"><span data-stu-id="87e1a-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="87e1a-125">Пример</span><span class="sxs-lookup"><span data-stu-id="87e1a-125">Example</span></span>  
 <span data-ttu-id="87e1a-126">В следующем примере показано, как создать оператор `join`, в котором одна сторона может принимать значение NULL, а другая сторона не может.</span><span class="sxs-lookup"><span data-stu-id="87e1a-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="87e1a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="87e1a-127">See also</span></span>

- [<span data-ttu-id="87e1a-128">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="87e1a-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
