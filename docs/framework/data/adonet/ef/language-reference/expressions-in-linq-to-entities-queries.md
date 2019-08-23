---
title: Выражения в запросах LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 383339241194c56d0c3178f538f2ac08b2f1b437
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950394"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="fc021-102">Выражения в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="fc021-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="fc021-103">Выражение представляет собой фрагмент кода, результатом вычисления которого является единственное значение, объект, метод или пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fc021-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="fc021-104">Выражение может содержать литеральное значение, вызов метода, оператор с операндами или простое имя.</span><span class="sxs-lookup"><span data-stu-id="fc021-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="fc021-105">Простые имена могут быть именами переменной, элемента типа, параметра метода, пространства имен или типа.</span><span class="sxs-lookup"><span data-stu-id="fc021-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="fc021-106">В выражениях могут использоваться операторы, которые, в свою очередь, используют в качестве параметров другие выражения или вызовы методов, параметрами которых являются другие вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="fc021-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="fc021-107">Таким образом, выражения могут быть как простыми, так и очень сложными.</span><span class="sxs-lookup"><span data-stu-id="fc021-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="fc021-108">В запросах LINQ to Entities выражения могут содержать все, что разрешено типами в <xref:System.Linq.Expressions> пространстве имен, включая лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="fc021-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="fc021-109">Выражения, которые можно использовать в запросах LINQ to Entities, представляют собой надмножество выражений, которые можно использовать для запроса [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc021-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="fc021-110">Выражения, которые являются частью запросов к, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ограничены операциями, `ObjectQuery<T>` поддерживаемыми и базовым источником данных.</span><span class="sxs-lookup"><span data-stu-id="fc021-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="fc021-111">В следующем примере сравнение в предложении `Where` является следующим выражением.</span><span class="sxs-lookup"><span data-stu-id="fc021-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="fc021-112">Отдельные языковые конструкции, такие как C# `unchecked`, не имеют смысла в LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="fc021-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc021-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fc021-113">In This Section</span></span>  
 [<span data-ttu-id="fc021-114">Константные выражения</span><span class="sxs-lookup"><span data-stu-id="fc021-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="fc021-115">Выражения сравнения</span><span class="sxs-lookup"><span data-stu-id="fc021-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="fc021-116">Сравнения NULL</span><span class="sxs-lookup"><span data-stu-id="fc021-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="fc021-117">Выражения инициализации</span><span class="sxs-lookup"><span data-stu-id="fc021-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="fc021-118">Связи, свойства навигации и внешние ключи</span><span class="sxs-lookup"><span data-stu-id="fc021-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="fc021-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fc021-119">See also</span></span>

- [<span data-ttu-id="fc021-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fc021-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
