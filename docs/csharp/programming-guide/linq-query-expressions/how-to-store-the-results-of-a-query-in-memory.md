---
redirect_url: /dotnet/articles/csharp/linq/store-the-results-of-a-query-in-memory
caps.handback.revision: 13
---
# Практическое руководство. Сохранение результатов запроса в памяти (Руководство по программированию в C#)
Запрос, по сути своей является набором инструкций, на основании которых осуществляется извлечение и организация данных.  Для выполнения запроса требуется вызов его метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.  Этот вызов выполняется при использовании цикла `foreach` для итерации элементов.  Для оценки запроса и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.  
  
## Пример  
 [!code-cs[csProgGuideLINQ#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  
## Компиляция кода  
  
-   Создайте проект [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)], предназначенный для платформы .NET Framework версии 3.5.  По умолчанию в проекте имеются ссылка на файл System.Core.dll и директива `using` \(C\#\) для пространства имен System.Linq.  
  
-   Скопируйте код в созданный проект.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить программу.  
  
-   Нажмите любую клавишу для выхода из окна консоли.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)