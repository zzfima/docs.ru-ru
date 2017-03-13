---
redirect_url: /dotnet/articles/csharp/linq/create-a-nested-group
caps.handback.revision: 12
---
# Практическое руководство. Создание вложенной группы (Руководство по программированию на C#)
В следующем примере показано, как создавать вложенные группы в выражении запроса [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  Каждая группа, созданная в соответствии с годом или уровнем обучения, затем подразделяется на группы на основе имен учащихся.  
  
## Пример  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-create-a-nested-group_1.cs)]  
  
 Обратите внимание на то, что для выполнения итерации по внутренним элементам вложенной группы необходимы три вложенных цикла `foreach`.  
  
## Компиляция кода  
 В этом примере содержатся ссылки на объекты, определенные в примере приложения в разделе [Практическое руководство. Запрос коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md).  Чтобы скомпилировать и запустить этот метод, вставьте его в класс `StudentClass` в этом приложении и добавьте его вызов из метода `Main`.  
  
 Настраивая данный метод для своего приложения, помните, что для LINQ требуется [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] версии 3.5, и проект должен содержать ссылку на библиотеку System.Core.dll и директиву Using для библиотеки System.Linq.  Типы LINQ to SQL, LINQ to XML и LINQ to DataSet требуют дополнительных директив Using и ссылок.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)