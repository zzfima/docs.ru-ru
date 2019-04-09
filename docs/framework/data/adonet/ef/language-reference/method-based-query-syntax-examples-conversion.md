---
title: Примеры синтаксиса запросов на основе методов. Преобразование
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: bf6c889fff2635cd50597e72151c46fbb4d9b97d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150622"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="ec380-102">Примеры синтаксиса запросов на основе методов. Преобразование</span><span class="sxs-lookup"><span data-stu-id="ec380-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="ec380-103">Примеры в этом разделе демонстрируют, как использовать <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> и <xref:System.Linq.Enumerable.ToList%2A> методы запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с использованием синтаксиса запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="ec380-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="ec380-104">Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ec380-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ec380-105">В примерах в этом разделе используются следующие `using` / `Imports` инструкции:</span><span class="sxs-lookup"><span data-stu-id="ec380-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="ec380-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="ec380-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="ec380-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ec380-107">Example</span></span>  
 <span data-ttu-id="ec380-108">В следующем примере метод <xref:System.Linq.Enumerable.ToArray%2A> вызывается для немедленного вычисления последовательности с получением массива.</span><span class="sxs-lookup"><span data-stu-id="ec380-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="ec380-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="ec380-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="ec380-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ec380-110">Example</span></span>  
 <span data-ttu-id="ec380-111">В следующем примере используется метод <xref:System.Linq.Enumerable.ToDictionary%2A> для немедленного вычисления последовательности и связанного с нею ключевого выражения с получением словаря.</span><span class="sxs-lookup"><span data-stu-id="ec380-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="ec380-112">ToList</span><span class="sxs-lookup"><span data-stu-id="ec380-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="ec380-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ec380-113">Example</span></span>  
 <span data-ttu-id="ec380-114">В следующем примере используется метод <xref:System.Linq.Enumerable.ToList%2A> для немедленного вычисления последовательности с получением коллекции <xref:System.Collections.Generic.List%601>, где параметр `T` относится к типу <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="ec380-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="ec380-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ec380-115">See also</span></span>

- [<span data-ttu-id="ec380-116">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ec380-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
