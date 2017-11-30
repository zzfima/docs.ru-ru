---
title: "Практическое руководство. Формулировка запросов-объединений и запросов векторного произведения"
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
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 703823368f451839304ce02ff8b5f7259a44b935
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="a82e6-102">Практическое руководство. Формулировка запросов-объединений и запросов векторного произведения</span><span class="sxs-lookup"><span data-stu-id="a82e6-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="a82e6-103">В следующем примере показано, как объединить результаты из нескольких таблиц.</span><span class="sxs-lookup"><span data-stu-id="a82e6-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a82e6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-104">Example</span></span>  
 <span data-ttu-id="a82e6-105">В следующем примере используется переходы по внешним ключам в `From` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` предложение в C#) для выбора всех заказов для клиентов в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="a82e6-105">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-106">Example</span></span>  
 <span data-ttu-id="a82e6-107">В следующем примере используется переходы по внешним ключам в `Where` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` предложение в C#) для фильтрации из за `Products` которого `Supplier` находится в США.</span><span class="sxs-lookup"><span data-stu-id="a82e6-107">The following example uses foreign key navigation in the `Where` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-108">Example</span></span>  
 <span data-ttu-id="a82e6-109">В следующем примере для фильтрации сотрудников, расположенных в Сиэтле, и получения списка закрепленных за ними регионов, используются переходы по внешним ключам в предложении `From` языка [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (предложении `from` языка C#).</span><span class="sxs-lookup"><span data-stu-id="a82e6-109">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-110">Example</span></span>  
 <span data-ttu-id="a82e6-111">В следующем примере используется переходы по внешним ключам в `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) для фильтрации пар сотрудников, в которых один сотрудник сообщает о другом и оба сотрудника находятся в одном `City`.</span><span class="sxs-lookup"><span data-stu-id="a82e6-111">The following example uses foreign key navigation in the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-112">Example</span></span>  
 <span data-ttu-id="a82e6-113">Следующие [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] примере выполняется поиск всех клиентов и заказов, гарантирует, что совпадение заказы для клиентов и гарантирует, что для каждого клиента в этом списке контактное лицо.</span><span class="sxs-lookup"><span data-stu-id="a82e6-113">The following [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-114">Example</span></span>  
 <span data-ttu-id="a82e6-115">В следующем пример явно соединяются две таблицы и проецируются результаты из обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="a82e6-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-116">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-116">Example</span></span>  
 <span data-ttu-id="a82e6-117">В следующем пример явно соединяются три таблицы и проецируются результаты из каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="a82e6-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-118">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-118">Example</span></span>  
 <span data-ttu-id="a82e6-119">В следующем примере показано, как реализовать оператор `LEFT OUTER JOIN` с помощью метода `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="a82e6-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="a82e6-120">Если для сотрудника (`DefaultIfEmpty()`) не имеется заказов (`Order`), метод `Employee` возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a82e6-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-121">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-121">Example</span></span>  
 <span data-ttu-id="a82e6-122">В следующем примере проецируется выражение `let`, полученное в результате соединения.</span><span class="sxs-lookup"><span data-stu-id="a82e6-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-123">Example</span></span>  
 <span data-ttu-id="a82e6-124">В следующем примере показан оператор `join` с композитным ключом.</span><span class="sxs-lookup"><span data-stu-id="a82e6-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="a82e6-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a82e6-125">Example</span></span>  
 <span data-ttu-id="a82e6-126">В следующем примере показано, как создать оператор `join`, в котором одна сторона может принимать значение NULL, а другая сторона не может.</span><span class="sxs-lookup"><span data-stu-id="a82e6-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="a82e6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a82e6-127">See Also</span></span>  
 [<span data-ttu-id="a82e6-128">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="a82e6-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
