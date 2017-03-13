---
redirect_url: /dotnet/articles/csharp/linq/order-the-results-of-a-join-clause
caps.handback.revision: 6
---
# Практическое руководство. Упорядочение результатов предложения соединения (Руководство по программированию на C#)
В этом примере показано, как упорядочить результаты операции соединения.  Обратите внимание, что упорядочение выполняется после соединения.  Хотя до выполнения соединения можно использовать предложение `orderby` с указанием одной или нескольких исходных последовательностей, это делать не рекомендуется.  Некоторые поставщики [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] могут не сохранять этот порядок после соединения.  
  
## Пример  
 Этот запрос создает группу соединения, а затем сортирует группы на основе элемента категории, который все еще находится в области действия.  Внутри анонимного инициализатора элементов вложенный запрос упорядочивает все соответствующие элементы из последовательности продуктов.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-order-the-results-of-a-join-clause_1.cs)]  
  
## Компиляция кода  
  
-   Создайте проект [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)], предназначенный для платформы .NET Framework версии 3.5.  По умолчанию в проекте имеются ссылка на файл System.Core.dll и директива `using` \(C\#\) для пространства имен System.Linq.  
  
-   Скопируйте код в созданный проект.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить программу.  
  
-   Нажмите любую клавишу для выхода из окна консоли.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение orderby](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [Предложение join](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)