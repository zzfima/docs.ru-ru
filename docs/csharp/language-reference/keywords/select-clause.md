---
title: "Предложение &quot;select&quot; (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "select_CSharpKeyword"
  - "select"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "select - предложение [C#]"
  - "select - ключевое слово [C#]"
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Предложение &quot;select&quot; (справочник по C#)
В выражении запроса предложение `select` задает тип значений, получаемых при выполнении запроса.  Результат основывается на анализе всех предыдущих предложений и на любых выражениях внутри предложения `select`.  Выражение запроса должно завершаться предложением `select` или [group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 В следующем примере демонстрируется простое предложение `select` в выражении запроса.  
  
 [!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Select.cs#8)]  
  
 Тип последовательности, созданной предложением `select`, определяет тип переменной запроса `queryHighScores`.  В простейшем случае предложение `select` просто задает переменную диапазона.  В результате возвращенная последовательность содержит элементы с тем же типом, что и у элементов в источнике данных.  Дополнительные сведения см. в разделе [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  Тем не менее, предложение `select` также предоставляет мощный механизм для преобразования \(или *выполнения проекции*\) исходных данных в новые типы.  Дополнительные сведения см. в разделе [Преобразования данных с помощью LINQ \(C\#\)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## Пример  
 В следующем примере программы показаны все различные формы, которые может иметь предложение `select`.  Обратите внимание на отношение в каждом запросе между предложением `select` и типом *переменной запроса* \(`studentQuery1`, `studentQuery2` и т. д.\).  
  
 [!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Select.cs#9)]  
  
 Как показано на вышеприведенном примере `studentQuery8`, иногда требуется, чтобы элементы возвращенной последовательности содержали только подмножество свойств исходных элементов.  Обеспечивая как можно меньший размер возвращенной последовательности, можно уменьшить требования к памяти и увеличить скорость выполнения запроса.  Для этого можно создать в предложении `select` анонимный тип и с помощью инициализатора объекта инициализировать этот тип с требуемыми свойствами исходного элемента.  Пример того, как это сделать содержится в разделе [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Заметки  
 Во время компиляции предложение `select` переводится в вызов метода к стандартному оператору запроса <xref:System.Linq.Enumerable.Select%2A>.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Ключевые слова запроса \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Предложение from](../../../csharp/language-reference/keywords/from-clause.md)   
 [разделяемый \(метод\) \(Справочник по C\#\)](../../../csharp/language-reference/keywords/partial-method.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)