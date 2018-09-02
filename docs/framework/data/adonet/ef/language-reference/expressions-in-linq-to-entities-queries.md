---
title: Выражения в запросах LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: dccf3ab1a619222cdf2db54673718eb103aee2fb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422273"
---
# <a name="expressions-in-linq-to-entities-queries"></a>Выражения в запросах LINQ to Entities
Выражение представляет собой фрагмент кода, результатом вычисления которого является единственное значение, объект, метод или пространство имен. Выражение может содержать литеральное значение, вызов метода, оператор с операндами или простое имя. Простые имена могут быть именами переменной, элемента типа, параметра метода, пространства имен или типа. В выражениях могут использоваться операторы, которые, в свою очередь, используют в качестве параметров другие выражения или вызовы методов, параметрами которых являются другие вызовы методов. Таким образом, выражения могут быть как простыми, так и очень сложными.  
  
 В [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] запросы, выражения могут содержать любые конструкции, допустимые типами в <xref:System.Linq.Expressions> пространства имен, включая лямбда-выражения. Набор выражений, используемых в запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], является надмножеством выражений, которые могут использоваться в запросах [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Выражения, которые являются частью запросы к [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ограничены операции, поддерживаемые `ObjectQuery<T>` и базовом источнике данных.  
  
 В следующем примере сравнение в предложении `Where` является следующим выражением.  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  Особые языковые конструкции, такие как `unchecked` в C#, в [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] значения не имеют.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Константные выражения](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Выражения сравнения](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [Сравнения NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Выражения инициализации](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Свойства навигации](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a>См. также  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
