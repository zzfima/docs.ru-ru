---
title: "Группировка элементов последовательности"
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
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9a398bb7b951fcf2dd2449b6468a19d39a134a4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="58cd7-102">Группировка элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="58cd7-102">Group Elements in a Sequence</span></span>
<span data-ttu-id="58cd7-103">Оператор <xref:System.Linq.Enumerable.GroupBy%2A> группирует элементы последовательности.</span><span class="sxs-lookup"><span data-stu-id="58cd7-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="58cd7-104">В следующем примере используется база данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="58cd7-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58cd7-105">Иногда значения NULL в столбцах в запросах <xref:System.Linq.Enumerable.GroupBy%2A> могут вызывать исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="58cd7-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="58cd7-106">Дополнительные сведения см. раздел «GroupBy InvalidOperationException» [Устранение неполадок](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="58cd7-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58cd7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-107">Example</span></span>  
 <span data-ttu-id="58cd7-108">Следующий пример разделяет `Products` по `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="58cd7-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-109">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-109">Example</span></span>  
 <span data-ttu-id="58cd7-110">В следующем примере для нахождения максимальной цены за единицу для каждого <xref:System.Linq.Enumerable.Max%2A> используется `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="58cd7-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-111">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-111">Example</span></span>  
 <span data-ttu-id="58cd7-112">В следующем примере для нахождения среднего значения `UnitPrice` для каждого `CategoryID` используется функция Average.</span><span class="sxs-lookup"><span data-stu-id="58cd7-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-113">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-113">Example</span></span>  
 <span data-ttu-id="58cd7-114">В следующем примере для нахождения общего значения <xref:System.Linq.Queryable.Sum%2A> для каждого `UnitPrice` используется `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="58cd7-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-115">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-115">Example</span></span>  
 <span data-ttu-id="58cd7-116">В следующем примере для нахождения в каждом <xref:System.Linq.Queryable.Count%2A> числа `Products`, производство которых прекращено, используется `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="58cd7-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-117">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-117">Example</span></span>  
 <span data-ttu-id="58cd7-118">В следующем примере для нахождения всех категорий, включающих как минимум 10 продуктов, используется предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="58cd7-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-119">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-119">Example</span></span>  
 <span data-ttu-id="58cd7-120">В следующем примере продукты сгруппированы по `CategoryID` и `SupplierID`.</span><span class="sxs-lookup"><span data-stu-id="58cd7-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-121">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-121">Example</span></span>  
 <span data-ttu-id="58cd7-122">В следующем примере возвращается две последовательности продуктов.</span><span class="sxs-lookup"><span data-stu-id="58cd7-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="58cd7-123">В первой последовательности находятся продукты, цена за единицу которых меньше или равна 10.</span><span class="sxs-lookup"><span data-stu-id="58cd7-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="58cd7-124">Во второй последовательности содержатся продукты, цена за единицу которых больше 10.</span><span class="sxs-lookup"><span data-stu-id="58cd7-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="58cd7-125">Пример</span><span class="sxs-lookup"><span data-stu-id="58cd7-125">Example</span></span>  
 <span data-ttu-id="58cd7-126">Оператор <xref:System.Linq.Queryable.GroupBy%2A> может принимает только один основной аргумент.</span><span class="sxs-lookup"><span data-stu-id="58cd7-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="58cd7-127">Если требуется выполнить группировку по нескольким признакам, следует создать анонимный тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="58cd7-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="58cd7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="58cd7-128">See Also</span></span>  
 [<span data-ttu-id="58cd7-129">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="58cd7-129">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="58cd7-130">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="58cd7-130">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
