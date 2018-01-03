---
title: "Выражения в запросах LINQ to Entities"
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
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6c1460aa78e112d29a4c500c54661b63de03e953
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="84e6a-102">Выражения в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="84e6a-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="84e6a-103">Выражение представляет собой фрагмент кода, результатом вычисления которого является единственное значение, объект, метод или пространство имен.</span><span class="sxs-lookup"><span data-stu-id="84e6a-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="84e6a-104">Выражение может содержать литеральное значение, вызов метода, оператор с операндами или простое имя.</span><span class="sxs-lookup"><span data-stu-id="84e6a-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="84e6a-105">Простые имена могут быть именами переменной, элемента типа, параметра метода, пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="84e6a-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="84e6a-106">В выражениях могут использоваться операторы, которые, в свою очередь, используют в качестве параметров другие выражения или вызовы методов, параметрами которых являются другие вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="84e6a-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="84e6a-107">Таким образом, выражения могут быть как простыми, так и очень сложными.</span><span class="sxs-lookup"><span data-stu-id="84e6a-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="84e6a-108">В [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] запросы, выражения могут содержать любые конструкции, допустимые типами в <xref:System.Linq.Expressions> пространства имен, включая лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="84e6a-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="84e6a-109">Набор выражений, используемых в запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], является надмножеством выражений, которые могут использоваться в запросах [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84e6a-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="84e6a-110">Выражения, которые являются частью запросы к [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ограничены операции, поддерживаемые `ObjectQuery<T>` и базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="84e6a-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="84e6a-111">В следующем примере сравнение в предложении `Where` является следующим выражением.</span><span class="sxs-lookup"><span data-stu-id="84e6a-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="84e6a-112">Особые языковые конструкции, такие как `unchecked` в C#, в [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] значения не имеют.</span><span class="sxs-lookup"><span data-stu-id="84e6a-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84e6a-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="84e6a-113">In This Section</span></span>  
 [<span data-ttu-id="84e6a-114">Константные выражения</span><span class="sxs-lookup"><span data-stu-id="84e6a-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="84e6a-115">Выражения сравнения</span><span class="sxs-lookup"><span data-stu-id="84e6a-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="84e6a-116">Сравнения NULL</span><span class="sxs-lookup"><span data-stu-id="84e6a-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="84e6a-117">Выражения инициализации</span><span class="sxs-lookup"><span data-stu-id="84e6a-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="84e6a-118">Свойства навигации</span><span class="sxs-lookup"><span data-stu-id="84e6a-118">Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a><span data-ttu-id="84e6a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="84e6a-119">See Also</span></span>  
 [<span data-ttu-id="84e6a-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="84e6a-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
