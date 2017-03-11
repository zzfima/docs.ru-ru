---
redirect_url: /dotnet/articles/csharp/linq/index
caps.handback.revision: 21
---
# Выражения запросов LINQ (Руководство по программированию на C#)
[!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext-md.md)] — это название набора технологий, основанных на интеграции возможностей запроса непосредственно в язык C\# \(а также в Visual Basic и, возможно, в любые другие языки .NET\).  Благодаря [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] запрос теперь является одним из основных структурных элементов языка, подобно классам, методам, событиям и т. д.  
  
 Для разработчиков, сознающих запросы, наиболее очевидная "встроенная в язык" часть [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] — это выражение запросов.  Выражения запросов составляются в соответствии с декларативным *синтаксисом запроса*, который был впервые предложен в C\# 3.0.  Синтаксис запроса позволяет выполнять достаточно сложную фильтрацию, упорядочение и операции группирования при работе с источниками данных, используя минимум программного кода.  Можно использовать одинаковые базовые шаблоны запросов для запроса и преобразования данных в базах данных SQL, наборах данных [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)], документах и потоках XML, а также в коллекциях .NET.  
  
 В следующем примере показана выполненная операция запроса.  Для выполнения операции запроса требуется создать источник данных, определить выражение запроса и выполнить запрос в операторе `foreach`.  
  
 [!code-cs[csProgGuideLINQ#11](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#11)]  
  
 Дополнительные сведения об основах [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] в C\# см. в разделе [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
## Общие сведения о выражениях запросов  
  
-   Выражения запросов можно использовать для запроса и преобразования данных, полученных из любого источника данных, поддерживающего [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  Например, один и тот же запрос может извлекать данные из базы данных SQL и на выходе создавать поток XML.  
  
-   Выражения запросов достаточно легко изучить, поскольку они во многом схожи с элементами языка C\#.  Дополнительные сведения см. в разделе [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
-   Все переменные в выражении запросов имеют строгую типизацию, хотя во многих случаях не требуется явным образом указывать тип, поскольку компилятор его вычисляет.  Дополнительные сведения см. в разделе [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
-   Выполнение запроса не происходит до использования переменной запроса в операторе `foreach`.  Дополнительные сведения см. в разделе [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   При компиляции выражения запросов преобразуется в вызовы методов стандартных операторов запроса согласно правилам, указанным в спецификациях языка C\#.  Любой запрос, которые может быть выражен с помощью синтаксиса запросов, также может быть выражен с помощью синтаксиса методов.  Однако синтаксис запросов в большинстве случаев понятнее и лаконичнее.  Дополнительные сведения см. в разделах [Спецификация языка C\#](../../../csharp/language-reference/language-specification.md) и [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
-   При создании запросов [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] рекомендуется использовать синтаксис запросов везде, где это возможно, и синтаксис методов, если это необходимо.  Между этими двумя видами не существует различий ни в семантике, ни в производительности.  Выражения запросов просто более понятны, чем соответствующие им выражения, написанные с помощью синтаксиса методов.  
  
-   Для некоторых операций запросов, таких как <xref:System.Linq.Enumerable.Count%2A> иди <xref:System.Linq.Enumerable.Max%2A>, нет соответствующих предложений в выражениях запросов, поэтому их необходимо создавать с помощью вызова методов.  Синтаксис запросов и синтаксиса методов можно сочетать друг с другом различными способами.  Дополнительные сведения см. в разделе [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
-   В зависимости от типа, к которому применяется запрос, выражения запросов можно компилировать в деревья выражений или в делегаты.  Запросы <xref:System.Collections.Generic.IEnumerable%601> компилируются в делегаты.  Запросы <xref:System.Linq.IQueryable> и <xref:System.Linq.IQueryable%601> компилируются в деревья выражений.  Дополнительные сведения см. в разделе [Деревья выражений](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
 В следующей таблице перечислены разделы, содержащие дополнительные сведения запросах и примеры кода для распространенных задач.  
  
|Раздел|Описание|  
|------------|--------------|  
|[Основы выражения запроса](../../../csharp/programming-guide/linq-query-expressions/query-expression-basics.md)|Описание основных принципов работы запросов, примеры синтаксиса запросов C\#.|  
|[Практическое руководство. Создание запросов LINQ на языке C\#](../../../csharp/programming-guide/linq-query-expressions/how-to-write-linq-queries.md)|Примеры нескольких базовых типов выражений запросов.|  
|[Практическое руководство. Обработка исключений в выражениях запросов](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)|Как и когда перемещать код, в котором могут возникнуть исключения, за пределы выражений запросов.|  
|[How to: Populate Object Collections from Multiple Sources \(LINQ\)](../Topic/How%20to:%20Populate%20Object%20Collections%20from%20Multiple%20Sources%20\(LINQ\).md)|Как использовать оператор `select` для слияния данных из разных источников в новый тип.|  
|[Практическое руководство. Группировка результатов запросов](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)|Различные способы использования предложения `group`.|  
|[Практическое руководство. Создание вложенной группы](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)|Демонстрация создания вложенных групп.|  
|[Практическое руководство. Вложенный запрос в операции группирования](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)|Демонстрация использования вложенных выражений в запросе в качестве источника данных для нового запроса.|  
|[Практическое руководство. Группирование результатов по смежным ключам](../../../csharp/programming-guide/linq-query-expressions/how-to-group-results-by-contiguous-keys.md)|Показано, как реализовать потокобезопасный стандартный оператор запроса, который может выполнять операции группирования на потоковых источниках данных.|  
|[Практическое руководство. Динамическое определение фильтров предикатов во время выполнения](../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)|Демонстрация предоставления произвольного числа значений для сравнения равенства в предложении `where`.|  
|[Практическое руководство. Сохранение результатов запроса в памяти](../../../csharp/programming-guide/linq-query-expressions/how-to-store-the-results-of-a-query-in-memory.md)|Демонстрация материализации и хранения результатов запросов без обязательного использования цикла `foreach`.|  
|[Практическое руководство. Возврат запроса из метода](../../../csharp/programming-guide/linq-query-expressions/how-to-return-a-query-from-a-method.md)|Демонстрация возврата переменных запросов из методов и передачи их методам в качестве входных параметров.|  
|[Практическое руководство. Выполнение пользовательских операций соединения](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)|Демонстрация операций соединения на основе функций предикатов любых видов.|  
|[Практическое руководство. Соединение с помощью составных ключей](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)|Демонстрация соединения двух источников на основе нескольких совпадающих ключей.|  
|[Практическое руководство. Упорядочение результатов предложения соединения](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)|Демонстрация упорядочения последовательности, созданной в результате операции соединения.|  
|[Практическое руководство. Выполнение внутренних соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)|Демонстрация выполнения внутреннего соединения в [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].|  
|[Практическое руководство. Выполнение групповых соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)|Демонстрация выполнения группового соединения в [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].|  
|[Практическое руководство. Выполнение левых внешних соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)|Демонстрация выполнения левого внешнего соединения в [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].|  
|[Практическое руководство. Обработка значений NULL в выражениях запросов](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-null-values-in-query-expressions.md)|Демонстрация обработки значений null в запросах [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].|  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Basic LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)   
 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Ключевые слова запроса \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [How Linq to Objects Queries Work](http://go.microsoft.com/fwlink/?LinkId=112389)   
 [Reading and Writing Queries](http://go.microsoft.com/fwlink/?LinkId=112391)   
 [What is a collection?](http://go.microsoft.com/fwlink/?LinkId=112394)   
 [Link to Everything: A List of LINQ Providers](http://go.microsoft.com/fwlink/?LinkId=112411)