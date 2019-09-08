---
title: Примеры синтаксиса запросов на основе методов. Секционирование (LINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
ms.openlocfilehash: 7e01bd9702ae267f80ecf24de0c0cc90d638a84c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783593"
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a><span data-ttu-id="2504e-102">Примеры синтаксиса запросов на основе методов. Секционирование (LINQ</span><span class="sxs-lookup"><span data-stu-id="2504e-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span></span>
<span data-ttu-id="2504e-103">В примерах данного раздела показано, как использовать методы <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.TakeWhile%2A> для запросов к объекту <xref:System.Data.DataSet> с использованием синтаксиса выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="2504e-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A>, and <xref:System.Linq.Enumerable.TakeWhile%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="2504e-104">Метод, используемый в этих примерах, задается при [загрузке данных в набор данных.](loading-data-into-a-dataset.md) `FillDataSet`</span><span class="sxs-lookup"><span data-stu-id="2504e-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2504e-105">В примерах данного раздела используются таблицы Contact, Address, Product, SalesOrderHeader и SalesOrderDetail из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2504e-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2504e-106">В примерах этого раздела используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="2504e-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="2504e-107">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта LINQ to DataSet в Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2504e-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="2504e-108">Skip</span><span class="sxs-lookup"><span data-stu-id="2504e-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="2504e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2504e-109">Example</span></span>  
 <span data-ttu-id="2504e-110">В данном примере метод <xref:System.Linq.Enumerable.Skip%2A> используется для получения всех контактов из таблицы `Contact`, за исключением первых пяти.</span><span class="sxs-lookup"><span data-stu-id="2504e-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="2504e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="2504e-111">Example</span></span>  
 <span data-ttu-id="2504e-112">В данном примере используется метод <xref:System.Linq.Enumerable.Skip%2A> для получения всех адресов в Сиэтле (Seattle), кроме первых двух.</span><span class="sxs-lookup"><span data-stu-id="2504e-112">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a><span data-ttu-id="2504e-113">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="2504e-113">SkipWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="2504e-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2504e-114">Example</span></span>  
 <span data-ttu-id="2504e-115">В этом примере методы <xref:System.Linq.Enumerable.OrderBy%2A> и <xref:System.Linq.Enumerable.SkipWhile%2A> используются для получения из таблицы `Product` продуктов, цена которых по прейскуранту составляет более 300,00.</span><span class="sxs-lookup"><span data-stu-id="2504e-115">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.SkipWhile%2A> methods to return products from the `Product` table with a list price greater than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a><span data-ttu-id="2504e-116">Take</span><span class="sxs-lookup"><span data-stu-id="2504e-116">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="2504e-117">Пример</span><span class="sxs-lookup"><span data-stu-id="2504e-117">Example</span></span>  
 <span data-ttu-id="2504e-118">В данном примере метод <xref:System.Linq.Enumerable.Take%2A> используется для получения только первых пяти контактов из таблицы `Contact`.</span><span class="sxs-lookup"><span data-stu-id="2504e-118">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="2504e-119">Пример</span><span class="sxs-lookup"><span data-stu-id="2504e-119">Example</span></span>  
 <span data-ttu-id="2504e-120">В данном примере используется метод <xref:System.Linq.Enumerable.Take%2A> для получения первых трех адресов в Сиэтле (Seattle).</span><span class="sxs-lookup"><span data-stu-id="2504e-120">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a><span data-ttu-id="2504e-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="2504e-121">TakeWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="2504e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="2504e-122">Example</span></span>  
 <span data-ttu-id="2504e-123">В этом примере методы <xref:System.Linq.Enumerable.OrderBy%2A> и <xref:System.Linq.Enumerable.TakeWhile%2A> используются для получения из таблицы `Product` продуктов, цена которых по прейскуранту составляет менее 300,00.</span><span class="sxs-lookup"><span data-stu-id="2504e-123">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.TakeWhile%2A> to return products from the `Product` table with a list price less than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="2504e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2504e-124">See also</span></span>

- [<span data-ttu-id="2504e-125">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="2504e-125">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="2504e-126">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2504e-126">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="2504e-127">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="2504e-127">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="2504e-128">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2504e-128">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
