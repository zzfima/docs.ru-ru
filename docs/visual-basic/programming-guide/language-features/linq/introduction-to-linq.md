---
title: "Знакомство с LINQ в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "отложенное выполнение"
  - "переменные итераций"
  - "LINQ"
  - "LINQ [Visual Basic]"
  - "LINQ [Visual Basic], сведения о LINQ в Visual Basic"
  - "запросы [LINQ в Visual Basic], сведения о LINQ в запросах Visual Basic"
  - "выполнение запроса [LINQ в Visual Basic]"
  - "выражения запроса [LINQ в Visual Basic]"
  - "переменные диапазона"
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Знакомство с LINQ в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Встроенные в язык запросы \(LINQ\) позволяют использовать запросы в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] и предоставляют простые, но эффективные средства для работы с любыми видами данных.  Технология LINQ позволяет не отправлять запросы на обработку в базу данных и не разрабатывать отдельный синтаксис запросов для каждого типа искомых данных, а вводит запросы в состав языка [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Синтаксис запросов не зависит от типа данных.  
  
 LINQ позволяет запрашивать данные из базы данных SQL Server, XML, а также хранящихся в памяти массивов и коллекций, наборов данных [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] и других локальных или удаленных источников, поддерживающих эту технологию.  Все это можно делать с помощью обычных элементов языка [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Поскольку запросы составляются на языке [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], их результаты возвращаются в виде строго типизированных объектов.  Эти объекты поддерживают технологию IntelliSense, что позволяет писать код быстрее и перехватывать ошибки в запросах при компиляции, а не при выполнении.  Запросы LINQ можно использовать как источник дополнительных запросов для уточнения результатов,  а также связывать с элементами управления, позволяя пользователям легко просматривать и изменять результаты запросов.  
  
 Например в следующем примере кода показан запрос LINQ, возвращающий список заказчиков из коллекции и группирующий их по расположению.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_1.vb)]  
  
 В этом разделе содержатся сведения о следующих областях:  
  
-   [Выполнение примеров](#RunningtheExamples)  
  
-   [Поставщики LINQ](#LINQProviders)  
  
-   [Структура запроса LINQ](#StructureOfALINQQuery)  
  
-   [Операторы запросов LINQ в Visual Basic](#VisualBasicLINQQueryOperators)  
  
-   [Подключение к базе данных с помощью LINQ to SQL](#ConnectingToADatabase)  
  
-   [Возможности Visual Basic, поддерживающие LINQ](#VisualBasicFeaturesThatSupportLINQ)  
  
-   [Отложенное и немедленное выполнение запроса](#QueryExecution)  
  
-   [XML в Visual Basic](#XMLInVisualBasic)  
  
-   [Связанные ресурсы](#RelatedResources)  
  
-   [Практические и пошаговые руководства](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a> Выполнение примеров  
 Для выполнения примеров, приведенных во введении и в разделе «Структура запроса LINQ», используйте указанный ниже код, который возвращает список клиентов и заказов.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_2.vb)]  
  
##  <a name="LINQProviders"></a> Поставщики LINQ  
 *Поставщик LINQ* сопоставляет ваши запросы LINQ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] с запрашиваемым источником данных.  При написании запроса LINQ поставщик принимает запрос и переводит его в команды, которые источник данных будет способен выполнить.  Затем поставщик преобразует данные из источника в объекты, составляющие результат запроса.  И, наконец, при отправке обновлений на источник данных он преобразует объекты в данные.  
  
 В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] входят следующие поставщики LINQ:  
  
|||  
|-|-|  
|Поставщик|Описание|  
|LINQ to Objects|Поставщик LINQ to Objects позволяет направлять запросы к коллекциям и массивам, которые находятся в памяти.  Если объект поддерживает интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>, поставщик LINQ to Objects позволяет направлять к нему запросы.<br /><br /> Поставщик LINQ to Objects включается при импорте пространства имен <xref:System.Linq>, которое импортируется по умолчанию для всех проектов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].<br /><br /> Дополнительные сведения о поставщике LINQ to Objects см. в разделе [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Поставщик LINQ to SQL позволяет запрашивать и изменять данные в базе данных SQL Server.  Это упрощает сопоставление объектной модели приложения с таблицами и объектами в базе данных.<br /><br /> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] упрощает работу с LINQ to SQL включением реляционного конструктора объектов \(O\/R\-конструктора\).  Он используется для создания в приложении модели объекта, которая сопоставляется с объектами в базе данных. Реляционный конструктор объектов также предоставляет функциональные возможности для сопоставления хранимых процедур и функций с объектом <xref:System.Data.Linq.DataContext>, который управляет связью с базой данных и сохраняет состояние проверок на оптимистичный параллелизм.<br /><br /> Дополнительные сведения о поставщике LINQ to SQL см. в разделе [LINQ to SQL](../Topic/LINQ%20to%20SQL.md).  Дополнительные сведения о реляционном конструкторе объектов см. в разделе [Реляционный конструктор объектов](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Поставщик LINQ to XML позволяет запрашивать и изменять XML.  XML можно изменить в памяти, загрузить из файла и сохранить в файл.<br /><br /> Кроме того, поставщик LINQ to XML разрешает использовать литералы XML и свойств оси XML, что позволяет записывать XML непосредственно в код [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Поставщик LINQ to DataSet позволяет запрашивать и обновлять данные в наборе данных [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)].  Функции LINQ можно добавить в приложения, использующие наборы данных — это позволит упростить и расширить возможности составления запросов, статистической обработки и обновления данных в наборе данных.<br /><br /> Дополнительные сведения см. в разделе [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md).|  
  
##  <a name="StructureOfALINQQuery"></a> Структура запроса LINQ  
 Запрос LINQ, который часто называют *выражением запроса*, состоит из комбинации предложений запросов, определяющих источники данных и переменные итерации для запроса.  Выражение запроса может также включать инструкции для сортировки, фильтрации, группировки и присоединения либо формулы для применения к исходным данным.  Синтаксис выражения запроса напоминает синтаксис SQL, поэтому многие его элементы могут показаться вам знакомыми.  
  
 Выражение запроса начинается с предложения `From`.  Это предложение определяет исходные данные для запроса и переменные, которые используются для обращения к каждому элементу источника данных по отдельности.  Эти переменные называются *переменными диапазона* или *переменными итераций*.  Предложение `From` является обязательным для запросов, кроме запросов `Aggregate`, где предложение `From` использовать необязательно.  После определения области и источника запроса в предложении `From` или `Aggregate` можно добавить любую комбинацию предложений для уточнения запроса.  Дополнительные сведения о предложениях запросов см. в разделе «Операторы запросов LINQ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]» далее в этом разделе.  Например, следующий запрос определяет исходную коллекцию данных клиента как переменную `customers` и как итерационную переменную `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_3.vb)]  
  
 Данный пример составляет допустимый запрос сам по себе, однако особенно эффективным запрос становится при добавлении нескольких предложений, уточняющих его результат.  Например, предложение `Where` позволяет отфильтровать результат по одному или нескольким значениям.  Каждое выражение запроса — это одна строка кода, так что предложения можно просто добавлять в конец запроса.  Запрос можно разбить на несколько текстовых строк, чтобы сделать его более удобочитаемым. Для этого используется символ продолжения строки \(\_\).  В приведенном ниже примере кода показан пример запроса с предложением `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_4.vb)]  
  
 Другое эффективное предложение запроса — это предложение `Select`, которое позволяет возвращать из источника данных только избранные поля.  Запросы LINQ возвращают перечислимые коллекции строго типизированных объектов.  Запрос может вернуть коллекцию как анонимных, так и именованных типов.  Предложение `Select` позволяет вернуть из источника данных отдельное поле.  В этом случае типом возвращаемой коллекции является тип этого поля.  Кроме того, предложение `Select` позволяет вернуть из источника данных несколько полей.  В этом случае типом возвращаемой коллекции становится новый анонимный тип.  Возвращенные запросом поля можно сопоставить с полями указанного именованного типа.  В приведенном ниже примере кода показано выражение запроса, возвращающее коллекцию анонимных типов, члены которой заполняются данными из выбранных полей источника данных.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_5.vb)]  
  
 Запросы LINQ могут также использоваться для объединения нескольких источников данных и получения единого результата.  Это можно сделать с помощью одного или нескольких предложений `From` или с помощью предложений `Join` или `Group Join`.  В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов и возвращающее коллекцию анонимных типов, содержащих объединенные данные.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_6.vb)]  
  
 Для получения иерархического результата, содержащего коллекцию объектов клиента, в запросе можно использовать предложение `Group Join`.  Каждый объект клиента имеет свойство, содержащее коллекцию всех заказов этого клиента.  В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов в иерархический результат и возвращающее коллекцию анонимных типов.  Запрос возвращает тип, у которого есть свойство `CustomerOrders`, содержащее коллекцию данных заказов клиента.  У него также есть свойство `OrderTotal`, которое содержит общую сумму всех заказов этого клиента.  \(Этот запрос эквивалентен LEFT OUTER JOIN\).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_7.vb)]  
  
 Имеется несколько дополнительных операторов запросов LINQ, которые можно использовать для создания эффективных выражений запросов.  В следующем разделе описываются различные предложения запросов, которые можно использовать в выражениях запросов.  Дополнительные сведения о предложениях запросов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в Visual Basic см. в разделе [Запросы](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a> Операторы запросов LINQ в Visual Basic  
 Классы в пространствах имен <xref:System.Linq> и других пространствах имен, поддерживающих запросы LINQ \(в частности, System.Linq\), содержат методы создания и уточнения запросов с учетом нужд приложения.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] содержит ключевые слова для наиболее распространенных предложений запросов, описанные в приведенной ниже таблице.  
  
|||  
|-|-|  
|Термин|Определение|  
|[Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md)|Запрос должен начинаться с предложения `From` или `Aggregate`.  Предложение `From` определяет коллекцию источника и переменную итерации для запроса.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#7](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_8.vb)]|  
|[Предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md)|Необязательно.  Объявляет набор переменных итераций для запроса.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#8](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_9.vb)]<br /><br /> Если предложение `Select` не указано, то переменные итераций для запроса состоят из переменных итераций, указанных предложением `From` или `Aggregate`.|  
|[Предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md)|Необязательно.  Определяет условие фильтрации для запроса.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#9](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_10.vb)]|  
|[Предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Необязательно.  Определяет порядок сортировки для столбцов в запросе.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_11.vb)]|  
|[Предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md)|Необязательно.  Объединяет две коллекции в одну.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_12.vb)]|  
|[Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Необязательно.  Группирует элементы результата запроса.  Может использоваться для применения агрегатных функций к каждой группе.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_13.vb)]|  
|[Предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Необязательно.  Объединяет две коллекции в одну иерархическую коллекцию.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_14.vb)]|  
|[Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Запрос должен начинаться с предложения `From` или `Aggregate`.  Предложение `Aggregate` применяет к коллекции одну или несколько агрегатных функций.  Например, предложение `Aggregate` можно использовать для вычисления суммы всех возвращенных запросом элементов.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_15.vb)]<br /><br /> Предложение `Aggregate` можно также использовать для изменения запроса.  Например, с помощью предложения `Aggregate` можно произвести вычисление с соответствующей коллекцией запросов.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_16.vb)]|  
|[Предложение Let](../../../../visual-basic/language-reference/queries/let-clause.md)|Необязательно.  Вычисляет значение и присваивает его новой переменной в запросе.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_17.vb)]|  
|[Предложение Distinct](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Необязательно.  Ограничивает значения текущей переменной итерации, чтобы исключить повторяющиеся значения в результатах запроса.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#17](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_18.vb)]|  
|[Предложение Skip](../../../../visual-basic/language-reference/queries/skip-clause.md)|Необязательно.  Пропускает заданное число элементов в коллекции и возвращает остальные элементы.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#18](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_19.vb)]|  
|[Предложение Skip While](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Необязательно.  Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#19](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_20.vb)]|  
|[Предложение Take](../../../../visual-basic/language-reference/queries/take-clause.md)|Необязательно.  Возвращает указанное число идущих подряд элементов с начала коллекции.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#20](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_21.vb)]|  
|[Предложение Take While](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Необязательно.  Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы.  Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#21](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_22.vb)]|  
  
 Дополнительные сведения о предложениях запросов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в Visual Basic см. в разделе [Запросы](../../../../visual-basic/language-reference/queries/queries.md).  
  
 Обращаясь к членам перечислимых и доступных для запроса типов, предоставляемых технологией LINQ, можно использовать дополнительные возможности запросов LINQ.  Для этого на результат выражения запроса необходимо вызвать определенный оператор запроса.  Например, в приведенном ниже примере кода применяется метод <xref:System.Linq.Enumerable.Union%2A>, позволяющий объединить результаты двух запросов в один.  Для возвращения результата запроса в виде универсального списка используется метод <xref:System.Linq.Enumerable.ToList%2A>.  
  
 [!code-vb[VbVbalrIntroToLINQ#22](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/introduction-to-linq_23.vb)]  
  
 Сведения о дополнительных возможностях LINQ см. в разделе [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
##  <a name="ConnectingToADatabase"></a> Подключение к базе данных с помощью LINQ to SQL  
 В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для идентификации объектов базы данных SQL Server \(таблиц, представлений и хранимых процедур\), к которым необходимо получить доступ, используется файл LINQ to SQL.  Файл LINQ to SQL имеет расширение DBML.  
  
 При наличии допустимого подключения к базе данных SQL Server можно добавить в проект шаблон элемента **Классы LINQ to SQL**.  Это позволит отобразить реляционный конструктор объектов \(O\/R\-конструктор\).  O\/R\-конструктор дает возможность перетаскивать элементы, к которым нужно получить доступ в коде, из **обозревателя серверов** или **обозревателя баз данных** на поверхность конструктора.  Файл LINQ to SQL добавляет в проект объект <xref:System.Data.Linq.DataContext>.  Этот объект включает свойства и коллекции для таблиц и представлений, к которым нужно получить доступ, а также необходимые методы для хранимых процедур.  После сохранения изменений в файле LINQ to SQL \(DBML\) можно получить доступ к этим объектам в коде, обратившись к определенному O\/R\-конструктором объекту <xref:System.Data.Linq.DataContext>.  Объекту <xref:System.Data.Linq.DataContext> для проекта присваивается имя, которое определяется именем файла LINQ to SQL.  Например, файл LINQ to SQL с именем Northwind.dbml создаст объект <xref:System.Data.Linq.DataContext> с именем `NorthwindDataContext`.  
  
 Примеры с пошаговыми инструкциями см. в разделе [Практическое руководство. Выполнение запросов к базе данных](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) и [Практическое руководство. Вызов хранимой процедуры](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a> Возможности Visual Basic, поддерживающие LINQ  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] включает и другие возможности, упрощающие работу с технологией LINQ и уменьшающие размер кода, необходимый для выполнения запросов LINQ.  В число этих требований входят следующие:  
  
-   **Анонимные типы**, позволяющие создать новый тип на основе результатов запроса.  
  
-   **Неявно типизированные переменные**, позволяющие отложить указание типа и позволить компилятору передавать тип в соответствии с результатом запроса.  
  
-   **Методы расширения**, позволяющие расширять существующий тип своими собственными методами без изменения самого типа.  
  
 Дополнительные сведения см. в разделе [Visual Basic Features That Support LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a> Отложенное и немедленное выполнение запроса  
 Процессы выполнения и создания запросов разделены.  После создания запроса его выполнение инициируется отдельным механизмом.  Запрос может быть выполнен сразу после определения \(*немедленное выполнение*\), либо его определение сохраняется и запрос выполняется позднее \(*отложенное выполнение*\).  
  
 По умолчанию вновь созданный запрос автоматически не выполняется.  Вместо этого определение запроса сохраняется в переменной, которая используется для ссылки на результат этого запроса.  Если впоследствии код обращается к переменной результата запроса, например в рамках цикла `For…Next`, запрос выполняется.  Такой процесс называется *отложенным выполнением*.  
  
 Запросы могут также выполняться сразу после определения — это называется *немедленным выполнением*.  Немедленное выполнение можно инициировать с помощью метода, который требует доступа к отдельным элементам результата запроса.  Это может быть результатом использования агрегатных функций, таких как `Count`, `Sum`, `Average`, `Min` или `Max`.  Дополнительные сведения об агрегатных функциях см. в разделе [Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Принудительно вызвать немедленное выполнение запросов позволяют также методы `ToList` и `ToArray`.  Это пригодится в том случае, если требуется выполнить запрос немедленно и кэшировать результаты.  Дополнительные сведения об этих методах см. в разделе [Converting Data Types](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Дополнительные сведения о выполнении запросов см. в разделе [Написание первого запроса LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a> XML в Visual Basic  
 Возможности XML в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] включают литералы XML и свойства оси XML, что позволяет легко создать, использовать, запрашивать и изменять XML в коде.  Литералы XML позволяют записывать XML непосредственно в код.  Компилятор Visual Basic обрабатывает XML как объект данных первого класса.  
  
 В приведенном ниже примере кода показано, как создать элемент XML, получить доступ к его дочерним элементам и атрибутам и сделать запросы к содержимому элемента с помощью LINQ.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/introduction-to-linq_24.vb)]  
  
 Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a> Связанные ресурсы  
  
|||  
|-|-|  
|Раздел|Описание|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Описание возможностей XML в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], к которым можно делать запросы и которые позволяют включать XML в код [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] как объекты данных первого класса.|  
|[Запросы](../../../../visual-basic/language-reference/queries/queries.md)|Содержит справочные сведения о предложениях запросов, которые доступны в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].|  
|[LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ.|  
|[LINQ to SQL](../Topic/LINQ%20to%20SQL.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to SQL.|  
|[LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to Objects.|  
|[LINQ to ADO.NET](../Topic/LINQ%20to%20ADO.NET%20\(Portal%20Page\)1.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)].|  
|[LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a> Практические и пошаговые руководства  
 [Практическое руководство. Выполнение запросов к базе данных](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md)  
  
 [Практическое руководство. Вызов хранимой процедуры](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Практическое руководство. Изменение данных в базе данных](../../../../visual-basic/programming-guide/language-features/linq/how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Практическое руководство. Объединение данных с помощью соединений](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Практическое руководство. Сортировка результатов запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)  
  
 [Практическое руководство. Фильтрование результатов запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)  
  
 [Практическое руководство. Выполнение над данными функций Count, Sum и Average](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Практическое руководство. Нахождение минимального или максимального значения в результатах запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Пошаговое руководство. Создание классов LINQ to SQL \(реляционный конструктор объектов\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)  
  
 [Как назначить хранимые процедуры для выполнения обновлений, вставок и удалений \(реляционный конструктор объектов\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)  
  
## Главы в популярных книгах  
 [Chapter 17: LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) \(Глава 17: LINQ\) в книге [Programming Visual Basic 2008](http://go.microsoft.com/fwlink/?LinkId=195383) \(Программирование на Visual Basic 2008\)  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)   
 [Общие сведения о LINQ to DataSet](../Topic/LINQ%20to%20DataSet%20Overview.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Примеры LINQ](../Topic/LINQ%20Samples.md)   
 [Реляционный конструктор объектов](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2)   
 [Методы DataContext \(реляционный конструктор объектов\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)