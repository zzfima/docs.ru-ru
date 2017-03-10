---
redirect_url: /dotnet/articles/csharp/linq/group-query-results
caps.handback.revision: 19
---
# Практическое руководство. Группировка результатов запросов (Руководство по программированию на C#)
Группирование — одна из самых эффективных функций [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  В следующих примерах демонстрируются различные способы группирования данных:  
  
-   По отдельному свойству.  
  
-   По первой букве строкового свойства.  
  
-   По расчетному числовому диапазону.  
  
-   По логическому предикату или другому выражению.  
  
-   По составному ключу.  
  
 Кроме того, два последних запроса передают свои результаты в новый анонимный тип, содержащий только имя и фамилию студента.  Дополнительные сведения см. в разделе [Предложение group](../../../csharp/language-reference/keywords/group-clause.md).  
  
## Пример  
 Во всех примерах в данном разделе используются следующие вспомогательные классы и источники данных.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#15)]  
  
## Пример  
 В следующем примере показывается группировка элементов источника с помощью использования отдельного свойства элемента в качестве ключа группы.  В данном случае в качестве ключа используется `string`, фамилия учащегося.  Для ключа можно также использовать подстроку.  При операции группирования используется компаратор проверки на равенство, используемый по умолчанию для данного типа.  
  
 Вставьте приведенный ниже метод в класс `StudentClass`.  Измените оператор вызова в методе `Main` на `sc.GroupBySingleProperty()`.  
  
 [!code-cs[csProgGuideLINQ#17](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#17)]  
  
## Пример  
 В следующем примере показывается группировка элементов источника, когда в качестве ключа группы используется не свойство объекта.  В данном случае в качестве ключа используется первая буква фамилии учащегося.  
  
 Вставьте приведенный ниже метод в класс `StudentClass`.  Измените оператор вызова в методе `Main` на `sc.GroupBySubstring()`.  
  
 [!code-cs[csProgGuideLINQ#18](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#18)]  
  
## Пример  
 В следующем примере показывается группировка элементов источника с помощью использования числового диапазона в качестве ключа группы.  Затем запрос передает результаты в анонимный тип, содержащий только имя и фамилию, а также диапазон процентилей, к которому принадлежит студент.  Использование анонимного типа объясняется тем, что для отображения результатов не требуется использовать полный объект `Student`.  `GetPercentile` — это вспомогательная функция, которая вычисляет процент на основе средних результатов учащихся.  Метод возвращает целое число в диапазоне от 0 до 10.  
  
 [!code-cs[csProgGuideLINQ#50](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#50)]  
  
 Вставьте приведенный ниже метод в класс `StudentClass`.  Измените оператор вызова в методе `Main` на `sc.GroupByRange()`.  
  
 [!code-cs[csProgGuideLINQ#19](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#19)]  
  
## Пример  
 В следующем примере показывается группировка элементов источника с помощью выражения логического сравнения.  В этом примере логическое выражение проверяет значение среднего экзаменационного результата учащегося, превосходит ли оно 75 баллов.  Как и в предыдущих примерах, результаты передаются в анонимный тип, поскольку весь элемент источника не требуется.  Обратите внимание на то, что свойства в анонимном типе становятся свойствами в члене `Key`, а при выполнении запроса доступ к ним можно получить по имени.  
  
 Вставьте приведенный ниже метод в класс `StudentClass`.  Измените оператор вызова в методе `Main` на `sc.GroupByBoolean()`.  
  
 [!code-cs[csProgGuideLINQ#20](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#20)]  
  
## Пример  
 В следующем примере показано, как использовать анонимный тип для инкапсуляции ключа, содержащего несколько значений.  В данном случае в качестве первого значения ключа используется первая буква фамилии учащегося.  Второе значение ключа является логическим и указывает, набрал ли учащийся более 85 баллов на первом экзамене.  Группы можно сортировать по любому из свойств в данном ключе.  
  
 Вставьте приведенный ниже метод в класс `StudentClass`.  Измените оператор вызова в методе `Main` на `sc.GroupByCompositeKey()`.  
  
 [!code-cs[csProgGuideLINQ#21](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#21)]  
  
## Компиляция кода  
 Копируйте и вставьте каждый метод, подлежащий проверке, в класс `StudentClass`.  Добавьте оператор вызова для метода в метод `Main` и нажмите клавишу F5.  
  
 Настраивая данные методы для собственного приложения, важно помнить, что для LINQ требуется [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] версии 3.5 или 4 и что проект должен содержать ссылку на библиотеку System.Core.dll и директиву using для библиотеки System.Linq.  Типа LINQ to SQL, LINQ to XML и LINQ to DataSet требуют дополнительных директив using и ссылок.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.IGrouping%602>   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение group](../../../csharp/language-reference/keywords/group-clause.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Практическое руководство. Вложенный запрос в операции группирования](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)   
 [Практическое руководство. Создание вложенной группы](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [Grouping Data](../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)