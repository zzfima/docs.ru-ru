---
title: Выражения в запросах LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 6ec61a295f50fa64c484902ed811a627a22ee1c7
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828050"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="76f39-102">Выражения в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="76f39-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="76f39-103">Выражение представляет собой фрагмент кода, результатом вычисления которого является единственное значение, объект, метод или пространство имен.</span><span class="sxs-lookup"><span data-stu-id="76f39-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="76f39-104">Выражение может содержать литеральное значение, вызов метода, оператор с операндами или простое имя.</span><span class="sxs-lookup"><span data-stu-id="76f39-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="76f39-105">Простые имена могут быть именами переменной, элемента типа, параметра метода, пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="76f39-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="76f39-106">В выражениях могут использоваться операторы, которые, в свою очередь, используют в качестве параметров другие выражения или вызовы методов, параметрами которых являются другие вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="76f39-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="76f39-107">Таким образом, выражения могут быть как простыми, так и очень сложными.</span><span class="sxs-lookup"><span data-stu-id="76f39-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="76f39-108">В [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] запросы, выражения могут содержать любые конструкции, допустимые типами в <xref:System.Linq.Expressions> пространства имен, включая лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="76f39-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="76f39-109">Набор выражений, используемых в запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], является надмножеством выражений, которые могут использоваться в запросах [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76f39-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="76f39-110">Выражения, которые являются частью запросы к [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ограничены операции, поддерживаемые `ObjectQuery<T>` и базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="76f39-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="76f39-111">В следующем примере сравнение в предложении `Where` является следующим выражением.</span><span class="sxs-lookup"><span data-stu-id="76f39-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="76f39-112">Особые языковые конструкции, такие как `unchecked` в C#, в [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] значения не имеют.</span><span class="sxs-lookup"><span data-stu-id="76f39-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76f39-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="76f39-113">In This Section</span></span>  
 [<span data-ttu-id="76f39-114">Константные выражения</span><span class="sxs-lookup"><span data-stu-id="76f39-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="76f39-115">Выражения сравнения</span><span class="sxs-lookup"><span data-stu-id="76f39-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="76f39-116">Сравнения NULL</span><span class="sxs-lookup"><span data-stu-id="76f39-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="76f39-117">Выражения инициализации</span><span class="sxs-lookup"><span data-stu-id="76f39-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="76f39-118">Связи, свойства навигации и внешние ключи</span><span class="sxs-lookup"><span data-stu-id="76f39-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="76f39-119">См. также</span><span class="sxs-lookup"><span data-stu-id="76f39-119">See also</span></span>
- [<span data-ttu-id="76f39-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="76f39-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
