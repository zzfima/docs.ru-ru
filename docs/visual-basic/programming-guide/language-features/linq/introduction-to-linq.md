---
title: Введение в LINQ
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: 610f2a1020cc15f855b3ddfc0917e14aae34fb82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344941"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Знакомство с LINQ в Visual Basic
Language-Integrated Query (LINQ) adds query capabilities to Visual Basic and provides simple and powerful capabilities when you work with all kinds of data. Rather than sending a query to a database to be processed, or working with different query syntax for each type of data that you are searching, LINQ introduces queries as part of the Visual Basic language. Синтаксис запросов не зависит от типа данных.  
  
 LINQ enables you to query data from a SQL Server database, XML, in-memory arrays and collections, ADO.NET datasets, or any other remote or local data source that supports LINQ. You can do all this with common Visual Basic language elements. Because your queries are written in the Visual Basic language, your query results are returned as strongly-typed objects. Эти объекты поддерживают технологию IntelliSense, что позволяет писать код быстрее и перехватывать ошибки в запросах при компиляции, а не при выполнении. Запросы LINQ можно использовать как источник дополнительных запросов для уточнения результатов, а также связывать с элементами управления, позволяя пользователям легко просматривать и изменять результаты запросов.  
  
 Например в следующем примере кода показан запрос LINQ, возвращающий список заказчиков из коллекции и группирующий их по расположению.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Выполнение примеров  
 To run the examples in the introduction and in the [Structure of a LINQ Query](#structure-of-a-linq-query) section, include the following code, which returns lists of customers and orders.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ providers  
 A *LINQ provider* maps your Visual Basic LINQ queries to the data source being queried. При написании запроса LINQ поставщик принимает запрос и переводит его в команды, которые источник данных будет способен выполнить. Затем поставщик преобразует данные из источника в объекты, составляющие результат запроса. И, наконец, при отправке обновлений на источник данных он преобразует объекты в данные.  
  
 Visual Basic includes the following LINQ providers.  
  
|Поставщик|Описание|  
|---|---|  
|LINQ to Objects|Поставщик LINQ to Objects позволяет направлять запросы к коллекциям и массивам, которые находятся в памяти. Если объект поддерживает интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>, поставщик LINQ to Objects позволяет направлять к нему запросы.<br /><br /> You can enable the LINQ to Objects provider by importing the <xref:System.Linq> namespace, which is imported by default for all Visual Basic projects.<br /><br /> For more information about the LINQ to Objects provider, see [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Поставщик LINQ to SQL позволяет запрашивать и изменять данные в базе данных SQL Server. Это упрощает сопоставление объектной модели приложения с таблицами и объектами в базе данных.<br /><br /> Visual Basic makes it easier to work with LINQ to SQL by including the Object Relational Designer (O/R Designer). Он используется для создания в приложении модели объекта, которая сопоставляется с объектами в базе данных. The O/R Designer also provides functionality to map stored procedures and functions to the <xref:System.Data.Linq.DataContext> object, which manages communication with the database and stores state for optimistic concurrency checks.<br /><br /> For more information about the LINQ to SQL provider, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). For more information about the Object Relational Designer, see [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Поставщик LINQ to XML позволяет запрашивать и изменять XML. XML можно изменить в памяти, загрузить из файла и сохранить в файл.<br /><br /> Additionally, the LINQ to XML provider enables XML literals and XML axis properties that enable you to write XML directly in your Visual Basic code. For more information, see [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|The LINQ to DataSet provider enables you to query and update data in an ADO.NET dataset. Функции LINQ можно добавить в приложения, использующие наборы данных — это позволит упростить и расширить возможности составления запросов, статистической обработки и обновления данных в наборе данных.<br /><br /> Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Structure of a LINQ query  
 A LINQ query, often referred to as a *query expression*, consists of a combination of query clauses that identify the data sources and iteration variables for the query. Выражение запроса может также включать инструкции для сортировки, фильтрации, группировки и присоединения либо формулы для применения к исходным данным. Синтаксис выражения запроса напоминает синтаксис SQL, поэтому многие его элементы могут показаться вам знакомыми.  
  
 Выражение запроса начинается с предложения `From`. Это предложение определяет исходные данные для запроса и переменные, которые используются для обращения к каждому элементу источника данных по отдельности. These variables are named *range variables* or *iteration variables*. Предложение `From` является обязательным для запросов, кроме запросов `Aggregate`, где предложение `From` использовать необязательно. После определения области и источника запроса в предложении `From` или `Aggregate` можно добавить любую комбинацию предложений для уточнения запроса. For details about query clauses, see Visual Basic LINQ Query Operators later in this topic. Например, следующий запрос определяет исходную коллекцию данных клиента как переменную `customers` и как итерационную переменную `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Данный пример составляет допустимый запрос сам по себе, однако особенно эффективным запрос становится при добавлении нескольких предложений, уточняющих его результат. Например, предложение `Where` позволяет отфильтровать результат по одному или нескольким значениям. Каждое выражение запроса — это одна строка кода, так что предложения можно просто добавлять в конец запроса. You can break up a query across multiple lines of text to improve readability by using the underscore (\_) line-continuation character. В приведенном ниже примере кода показан пример запроса с предложением `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Другое эффективное предложение запроса — это предложение `Select`, которое позволяет возвращать из источника данных только избранные поля. Запросы LINQ возвращают перечислимые коллекции строго типизированных объектов. Запрос может вернуть коллекцию как анонимных, так и именованных типов. Предложение `Select` позволяет вернуть из источника данных отдельное поле. В этом случае типом возвращаемой коллекции является тип этого поля. Кроме того, предложение `Select` позволяет вернуть из источника данных несколько полей. В этом случае типом возвращаемой коллекции становится новый анонимный тип. Возвращенные запросом поля можно сопоставить с полями указанного именованного типа. В приведенном ниже примере кода показано выражение запроса, возвращающее коллекцию анонимных типов, члены которой заполняются данными из выбранных полей источника данных.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Запросы LINQ могут также использоваться для объединения нескольких источников данных и получения единого результата. Это можно сделать с помощью одного или нескольких предложений `From` или с помощью предложений `Join` или `Group Join`. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов и возвращающее коллекцию анонимных типов, содержащих объединенные данные.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Для получения иерархического результата, содержащего коллекцию объектов клиента, в запросе можно использовать предложение `Group Join`. Каждый объект клиента имеет свойство, содержащее коллекцию всех заказов этого клиента. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов в иерархический результат и возвращающее коллекцию анонимных типов. Запрос возвращает тип, у которого есть свойство `CustomerOrders`, содержащее коллекцию данных заказов клиента. У него также есть свойство `OrderTotal`, которое содержит общую сумму всех заказов этого клиента. (Этот запрос эквивалентен LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Имеется несколько дополнительных операторов запросов LINQ, которые можно использовать для создания эффективных выражений запросов. В следующем разделе описываются различные предложения запросов, которые можно использовать в выражениях запросов. For details about Visual Basic query clauses, see [Queries](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ query operators  

Классы в пространствах имен <xref:System.Linq> и других пространствах имен, поддерживающих запросы LINQ (в частности, System.Linq), содержат методы создания и уточнения запросов с учетом нужд приложения. Visual Basic includes keywords for the following common query clauses. For details about Visual Basic query clauses, see [Queries](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Предложение From

Either a [`From` clause](../../../../visual-basic/language-reference/queries/from-clause.md) or an `Aggregate` clause is required to begin a query. Предложение `From` определяет коллекцию источника и переменную итерации для запроса. Пример:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select - предложение

Необязательный. A [`Select` clause](../../../../visual-basic/language-reference/queries/select-clause.md) declares a set of iteration variables for a query. Пример:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Если предложение `Select` не указано, то переменные итераций для запроса состоят из переменных итераций, указанных предложением `From` или `Aggregate`.

### <a name="where-clause"></a>Предложение Where

Необязательный. A [`Where` clause](../../../../visual-basic/language-reference/queries/where-clause.md) specifies a filtering condition for a query. Пример:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By clause]

|Optional. An [`Order By` clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifies the sort order for columns in a query. Пример:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join - предложение

Необязательный. A [`Join` clause](../../../../visual-basic/language-reference/queries/join-clause.md) combines two collections into a single collection. Пример:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By - предложение

Необязательный. A [`Group By` clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) groups the elements of a query result. It can be used to apply aggregate functions to each group. Пример:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join - предложение

Необязательный. A [`Group Join` clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) combines two collections into a single hierarchical collection. Пример:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate - предложение

Either an [`Aggregate` clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) or a `From` clause is required to begin a query. Предложение `Aggregate` применяет к коллекции одну или несколько агрегатных функций. For example, you can use the `Aggregate` clause to calculate a sum for all the elements returned by a query, as the following example does.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

Предложение `Aggregate` можно также использовать для изменения запроса. Например, с помощью предложения `Aggregate` можно произвести вычисление с соответствующей коллекцией запросов. Пример:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let - предложение

Необязательный. A [`Let` clause](../../../../visual-basic/language-reference/queries/let-clause.md) computes a value and assigns it to a new variable in the query. Пример:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct - предложение

Необязательный. A `Distinct` clause restricts the values of the current iteration variable to eliminate duplicate values in query results. Пример:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip - предложение

Необязательный. A [`Skip` clause](../../../../visual-basic/language-reference/queries/skip-clause.md) bypasses a specified number of elements in a collection and then returns the remaining elements. Пример:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While - предложение

Необязательный. A [`Skip While` clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements. Пример:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take - предложение

Необязательный. A [`Take` clause](../../../../visual-basic/language-reference/queries/take-clause.md) returns a specified number of contiguous elements from the start of a collection. Пример:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While - предложение

Необязательный. A [`Take While` clause](../../../../visual-basic/language-reference/queries/take-while-clause.md) includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements. Пример:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Use additional LINQ query features  
  
Обращаясь к членам перечислимых и доступных для запроса типов, предоставляемых технологией LINQ, можно использовать дополнительные возможности запросов LINQ. Для этого на результат выражения запроса необходимо вызвать определенный оператор запроса. For example, the following example uses the <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> method to combine the results of two queries into one query result. Для возвращения результата запроса в виде универсального списка используется метод <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 For details about additional LINQ capabilities, see [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connect to a database by using LINQ to SQL  
 In Visual Basic, you identify the SQL Server database objects, such as tables, views, and stored procedures, that you want to access by using a LINQ to SQL file. Файл LINQ to SQL имеет расширение DBML.  
  
 When you have a valid connection to a SQL Server database, you can add a **LINQ to SQL Classes** item template to your project. Это позволит отобразить реляционный конструктор объектов (O/R-конструктор). The O/R Designer enables you to drag the items that you want to access in your code from the **Server Explorer**/**Database Explorer** onto the designer surface. Файл LINQ to SQL добавляет в проект объект <xref:System.Data.Linq.DataContext>. Этот объект включает свойства и коллекции для таблиц и представлений, к которым нужно получить доступ, а также необходимые методы для хранимых процедур. После сохранения изменений в файле LINQ to SQL (DBML) можно получить доступ к этим объектам в коде, обратившись к определенному O/R-конструктором объекту <xref:System.Data.Linq.DataContext>. Объекту <xref:System.Data.Linq.DataContext> для проекта присваивается имя, которое определяется именем файла LINQ to SQL. Например, файл LINQ to SQL с именем Northwind.dbml создаст объект <xref:System.Data.Linq.DataContext> с именем `NorthwindDataContext`.  
  
 For examples with step-by-step instructions, see [How to: Query a Database](how-to-query-a-database-by-using-linq.md) and [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic features that support LINQ  
 Visual Basic includes other notable features that make the use of LINQ simple and reduce the amount of code that you must write to perform LINQ queries. В число этих требований входят следующие:  
  
- **Anonymous types**, which enable you to create a new type based on a query result.  
  
- **Implicitly typed variables**, which enable you to defer specifying a type and let the compiler infer the type based on the query result.  
  
- **Extension methods**, which enable you to extend an existing type with your own methods without modifying the type itself.  
  
 For details, see [Visual Basic Features That Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Deferred and immediate query execution

 Процессы выполнения и создания запросов разделены. После создания запроса его выполнение инициируется отдельным механизмом. A query can be executed as soon as it is defined (*immediate execution*), or the definition can be stored and the query can be executed later (*deferred execution*).  
  
 По умолчанию вновь созданный запрос автоматически не выполняется. Вместо этого определение запроса сохраняется в переменной, которая используется для ссылки на результат этого запроса. Если впоследствии код обращается к переменной результата запроса, например в рамках цикла `For…Next`, запрос выполняется. This process is referred to as *deferred execution*.  
  
 Queries can also be executed when they are defined, which is referred to as *immediate execution*. Немедленное выполнение можно инициировать с помощью метода, который требует доступа к отдельным элементам результата запроса. Это может быть результатом использования агрегатных функций, таких как `Count`, `Sum`, `Average`, `Min` или `Max`. For more information about aggregate functions, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md).  
  
 Принудительно вызвать немедленное выполнение запросов позволяют также методы `ToList` и `ToArray`. Это пригодится в том случае, если требуется выполнить запрос немедленно и кэшировать результаты. For more information about these methods, see [Converting Data Types](../../concepts/linq/converting-data-types.md).  
  
 For more information about query execution, see [Writing Your First LINQ Query](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML в Visual Basic  
 The XML features in Visual Basic include XML literals and XML axis properties, which enable you easily to create, access, query, and modify XML in your code. Литералы XML позволяют записывать XML непосредственно в код. Компилятор Visual Basic обрабатывает XML как объект данных первого класса.  
  
 В приведенном ниже примере кода показано, как создать элемент XML, получить доступ к его дочерним элементам и атрибутам и сделать запросы к содержимому элемента с помощью LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 For more information, see [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Связанные ресурсы  
  
|Раздел|Описание|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describes the XML features in Visual Basic that can be queried and that enable you to include XML as first-class data objects in your Visual Basic code.|  
|[Запросы](../../../language-reference/queries/index.md)|Provides reference information about the query clauses that are available in Visual Basic.|  
|[Встроенный язык запросов LINQ](../../concepts/linq/index.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to Objects.|  
|[LINQ to ADO.NET (Страница портала)](../../concepts/linq/linq-to-adonet-portal-page.md)|Includes links to general information, programming guidance, and samples for LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>How to and walkthrough topics
 [How to: Query a Database](how-to-query-a-database-by-using-linq.md) (Практическое руководство. Выполнение запросов к базе данных)  
  
 [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md) (Практическое руководство. Вызов хранимой процедуры)  
  
 [How to: Modify Data in a Database](how-to-modify-data-in-a-database-by-using-linq.md) (Практическое руководство. Изменение данных в базе данных)  
  
 [How to: Combine Data with Joins](how-to-combine-data-with-linq-by-using-joins.md) (Практическое руководство. Объединение данных с помощью соединений)  
  
 [How to: Sort Query Results](how-to-sort-query-results-by-using-linq.md) (Практическое руководство. Сортировка результатов запроса)  
  
 [How to: Filter Query Results](how-to-filter-query-results-by-using-linq.md) (Практическое руководство. Фильтрование результатов запроса)  
  
 [How to: Count, Sum, or Average Data](how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)  
  
 [How to: Find the Minimum or Maximum Value in a Query Result](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)  
  
 [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Featured book chapters  
 [Chapter 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>См. также

- [Встроенный язык запросов LINQ](../../concepts/linq/index.md)
- [Общие сведения о LINQ to XML в Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Общие сведения о LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
