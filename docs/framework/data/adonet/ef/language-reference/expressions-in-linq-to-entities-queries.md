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
# <a name="expressions-in-linq-to-entities-queries"></a>Выражения в запросах LINQ to Entities
Выражение представляет собой фрагмент кода, результатом вычисления которого является единственное значение, объект, метод или пространство имен. Выражение может содержать литеральное значение, вызов метода, оператор с операндами или простое имя. Простые имена могут быть именами переменной, элемента типа, параметра метода, пространства имен или типа. В выражениях могут использоваться операторы, которые, в свою очередь, используют в качестве параметров другие выражения или вызовы методов, параметрами которых являются другие вызовы методов. Таким образом, выражения могут быть как простыми, так и очень сложными.  
  
 В запросах LINQ to Entities выражения могут содержать все, что разрешено типами в <xref:System.Linq.Expressions> пространстве имен, включая лямбда-выражения. Выражения, которые можно использовать в запросах LINQ to Entities, представляют собой надмножество выражений, которые можно использовать для запроса [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Выражения, которые являются частью запросов к, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ограничены операциями, `ObjectQuery<T>` поддерживаемыми и базовым источником данных.  
  
 В следующем примере сравнение в предложении `Where` является следующим выражением.  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> Отдельные языковые конструкции, такие как C# `unchecked`, не имеют смысла в LINQ to Entities.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Константные выражения](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Выражения сравнения](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [Сравнения NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Выражения инициализации](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Связи, свойства навигации и внешние ключи](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
