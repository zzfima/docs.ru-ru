---
title: Примеры синтаксиса запросов на основе методов. Операторы задания значений (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 481c0ed7e39b8f958ccdae01e4589d54b3ff2446
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783575"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="58691-102">Примеры синтаксиса запросов на основе методов. Операторы задания значений (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="58691-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="58691-103">В <xref:System.Linq.Enumerable.Distinct%2A>примерах этого раздела показано, как использовать операторы, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>и <xref:System.Linq.Enumerable.Union%2A> для выполнения операций сравнения на основе наборов строк данных.[ Загрузка данных в набор данных](loading-data-into-a-dataset.md) см. в <xref:System.Data.DataRowComparer>разделе [Сравнение строк DataRow](comparing-datarows-linq-to-dataset.md) для получения дополнительных сведений о.</span><span class="sxs-lookup"><span data-stu-id="58691-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](loading-data-into-a-dataset.md) See [Comparing DataRows](comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="58691-104">Метод, используемый в этих примерах, задается при [загрузке данных в набор данных.](loading-data-into-a-dataset.md) `FillDataSet`</span><span class="sxs-lookup"><span data-stu-id="58691-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="58691-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="58691-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="58691-106">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="58691-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="58691-107">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="58691-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="58691-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="58691-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="58691-109">Пример</span><span class="sxs-lookup"><span data-stu-id="58691-109">Example</span></span>  
 <span data-ttu-id="58691-110">В этом примере метод <xref:System.Linq.Enumerable.Distinct%2A> используется для удаления повторяющихся элементов в последовательности.</span><span class="sxs-lookup"><span data-stu-id="58691-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="58691-111">Исключения</span><span class="sxs-lookup"><span data-stu-id="58691-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="58691-112">Пример</span><span class="sxs-lookup"><span data-stu-id="58691-112">Example</span></span>  
 <span data-ttu-id="58691-113">В этом примере метод <xref:System.Linq.Enumerable.Except%2A> используется, чтобы вернуть контакты, которые есть в первой таблице, но отсутствуют во второй.</span><span class="sxs-lookup"><span data-stu-id="58691-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="58691-114">Пересечение</span><span class="sxs-lookup"><span data-stu-id="58691-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="58691-115">Пример</span><span class="sxs-lookup"><span data-stu-id="58691-115">Example</span></span>  
 <span data-ttu-id="58691-116">В этом примере используется метод <xref:System.Linq.Enumerable.Intersect%2A>, чтобы вернуть контакты, которые есть в обеих таблицах.</span><span class="sxs-lookup"><span data-stu-id="58691-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="58691-117">Объединение</span><span class="sxs-lookup"><span data-stu-id="58691-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="58691-118">Пример</span><span class="sxs-lookup"><span data-stu-id="58691-118">Example</span></span>  
 <span data-ttu-id="58691-119">В этом примере используется метод <xref:System.Linq.Enumerable.Union%2A> для возврата уникальных контактов из двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="58691-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="58691-120">См. также</span><span class="sxs-lookup"><span data-stu-id="58691-120">See also</span></span>

- [<span data-ttu-id="58691-121">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="58691-121">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="58691-122">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="58691-122">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="58691-123">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="58691-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="58691-124">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58691-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
