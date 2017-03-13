---
redirect_url: /dotnet/articles/csharp/linq/handle-null-values-in-query-expressions
caps.handback.revision: 6
---
# Практическое руководство. Обработка значений NULL в выражениях запросов (Руководство по программированию в C#)
В этом примере показана обработка значений NULL, которые могут встретиться в исходной коллекции.  Коллекция объектов, например <xref:System.Collections.Generic.IEnumerable%601>, может содержать элементы, значение которых равно [NULL](../../../csharp/language-reference/keywords/null.md).  Если исходная коллекция равняется NULL или содержит элемент, значение которого равно NULL, а запрос не обрабатывает значения NULL, то при выполнении запроса возникнет исключение <xref:System.NullReferenceException>.  
  
## Пример  
 В код можно включить механизм защиты, позволяющий избежать появления ссылок на значения NULL, как показано в следующем примере.  
  
 [!code-cs[csProgGuideLINQ#82](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 В приведенном выше примере предложение `where` позволяет отфильтровать все элементы NULL в последовательности категорий.  Такой подход не зависит от проверки на значения NULL в предложении join.  Условное выражение в этом примере работает потому, что значение `Products.CategoryID` имеет тип `int?` что является сокращенной записью для `Nullable<int>`.  
  
## Пример  
 Если в предложении join только один из ключей сравнения имеет тип значения, допускающий значения NULL, можно привести второй ключ в выражении запроса к типу, допускающему значение NULL.  В следующем примере предполагается, что `EmployeeID` — столбец значений типа `int?`:  
  
 [!code-cs[csProgGuideLINQ#83](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## См. также  
 <xref:System.Nullable%601>   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)