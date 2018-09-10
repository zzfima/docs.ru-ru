---
title: Предложение "select" (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: dcab29cdbe98b5e49463d9a2781d43d4b9ee9544
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516485"
---
# <a name="select-clause-c-reference"></a>Предложение "select" (справочник по C#)
В выражении запроса предложение `select` задает тип значений, которые будут получены при выполнении запроса. Получаемый результат зависит от вычисления всех предыдущих предложений и любых выражений в самом предложении `select`. Выражение запроса должно оканчиваться предложением `select` или [group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 В следующем примере показано простое предложение `select` в выражении запроса.  
  
 [!code-csharp[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]  
  
 Тип последовательности, создаваемой предложением `select`, определяет тип переменной запроса `queryHighScores`. В самом простом случае предложение `select` просто задает переменную диапазона. В этом случае возвращаемая последовательность содержит элементы того же типа, что и источник данных. Дополнительные сведения см. в разделе [Связи типов в операциях запроса LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md). Тем не менее предложение `select` также реализует эффективный механизм для преобразования (или *проецирования*) данных источника в новые типы. Дополнительные сведения см. в разделе [Преобразования данных с помощью LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные формы, которые может принимать предложение `select`. В каждом запросе обратите внимание на связь между предложением `select` и типом *переменной запроса* (`studentQuery1`, `studentQuery2` и т. д.).  
  
 [!code-csharp[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]  
  
 Как показано в `studentQuery8` в предыдущем примере, в некоторых случаях требуется, чтобы элементы возвращаемой последовательности содержали только подмножество свойств элементов источника. Максимально уменьшая размер возвращаемой последовательности, вы можете снизить требования к памяти и, соответственно, повысить скорость выполнения запроса. Это можно сделать, создав анонимный тип в предложении `select` и используя инициализатор объекта для его инициализации с соответствующими свойствами из элементов источника. Пример того, как это сделать, см. в разделе [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="remarks"></a>Примечания  
 Во время компиляции предложение `select` преобразуется в вызов метода <xref:System.Linq.Enumerable.Select%2A> стандартного оператора запроса.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
- [предложение from](../../../csharp/language-reference/keywords/from-clause.md)  
- [partial (метод) (справочник по C#)](../../../csharp/language-reference/keywords/partial-method.md)  
- [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
- [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [Приступая к работе с LINQ в C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
