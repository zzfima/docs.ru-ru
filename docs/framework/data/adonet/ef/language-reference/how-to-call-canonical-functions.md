---
title: "Практическое руководство. Вызов канонических функций"
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
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 97ad63ea2aeb5ef1ef1acd1988254e995dbc63e0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-canonical-functions"></a><span data-ttu-id="d8852-102">Практическое руководство. Вызов канонических функций</span><span class="sxs-lookup"><span data-stu-id="d8852-102">How to: Call Canonical Functions</span></span>
<span data-ttu-id="d8852-103">Класс <xref:System.Data.Objects.EntityFunctions> содержит методы, предоставляющие доступ к каноническим функциям для использования в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="d8852-103">The <xref:System.Data.Objects.EntityFunctions> class contains methods that expose canonical functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="d8852-104">Сведения о канонических функциях см. в разделе [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-104">For information about canonical functions, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8852-105">Методы <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> и <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> в классе <xref:System.Data.Objects.EntityFunctions> не имеют эквивалентных канонических функций.</span><span class="sxs-lookup"><span data-stu-id="d8852-105">The <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> and <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> methods in the <xref:System.Data.Objects.EntityFunctions> class do not have canonical function equivalents.</span></span>  
  
 <span data-ttu-id="d8852-106">Канонические функции, которые производят вычисление по ряду значений и возвращают одиночное значение (известные также как статистические канонические функции), могут вызываться напрямую.</span><span class="sxs-lookup"><span data-stu-id="d8852-106">Canonical functions that perform a calculation on a set of values and return a single value (also known as aggregate canonical functions) can be directly invoked.</span></span> <span data-ttu-id="d8852-107">Другие канонические функции могут вызываться только в составе запроса LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="d8852-107">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="d8852-108">Чтобы вызвать агрегатную функцию напрямую, ей необходимо передать экземпляр <xref:System.Data.Objects.ObjectQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="d8852-108">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="d8852-109">Дополнительные сведения см. в приведенном ниже втором примере.</span><span class="sxs-lookup"><span data-stu-id="d8852-109">For more information, see the second example below.</span></span>  
  
 <span data-ttu-id="d8852-110">Некоторые канонические функции можно вызвать с помощью методов среды CLR в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="d8852-110">You can call some canonical functions by using common language runtime (CLR) methods in LINQ to Entities queries.</span></span> <span data-ttu-id="d8852-111">Список методов среды CLR, которые сопоставляются с каноническими функциями см. в разделе [методов CLR с сопоставления канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="d8852-111">For a list of CLR methods that map to canonical functions, see [CLR Method to Canonical Function Mapping](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8852-112">Пример</span><span class="sxs-lookup"><span data-stu-id="d8852-112">Example</span></span>  
 <span data-ttu-id="d8852-113">В следующем примере используется [модели AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="d8852-113">The following example uses the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="d8852-114">В этом примере выполняется запрос LINQ to Entities, в котором используется метод <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> для возврата всех продуктов, для которых разница между датами `SellEndDate` и `SellStartDate` меньше 365 суток:</span><span class="sxs-lookup"><span data-stu-id="d8852-114">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> method to return all products for which the difference between `SellEndDate` and `SellStartDate` is less than 365 days:</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="d8852-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d8852-115">Example</span></span>  
 <span data-ttu-id="d8852-116">В следующем примере используется [модели AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="d8852-116">The following example uses the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="d8852-117">В этом примере напрямую вызывается статистическая функция <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> для возврата стандартного отклонения промежуточных итогов `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="d8852-117">The example calls the aggregate <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> method directly to return the standard deviation of `SalesOrderHeader` subtotals.</span></span> <span data-ttu-id="d8852-118">Обратите внимание, что в функцию передается экземпляр <xref:System.Data.Objects.ObjectQuery%601>, что позволяет вызывать ее, хотя она и не входит в состав запроса LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="d8852-118">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d8852-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d8852-119">See Also</span></span>  
 [<span data-ttu-id="d8852-120">Вызов функций в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d8852-120">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="d8852-121">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d8852-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
