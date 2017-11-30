---
title: "Знакомство с LINQ в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 64e01fdfc4951dc23cd7ce92941a367882b3b6bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-linq-in-visual-basic"></a>Знакомство с LINQ в Visual Basic
Встроенные в язык запросы (LINQ) позволяют использовать запросы в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] и предоставляют простые, но эффективные средства для работы с любыми видами данных. Технология LINQ позволяет не отправлять запросы на обработку в базу данных и не разрабатывать отдельный синтаксис запросов для каждого типа искомых данных, а вводит запросы в состав языка [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Синтаксис запросов не зависит от типа данных.  
  
 LINQ позволяет запрашивать данные из базы данных SQL Server, XML, в памяти массивов и коллекций, [!INCLUDE[vstecado](~/includes/vstecado-md.md)] наборы данных, и других локальных или удаленных источников, поддерживающих эту технологию. Все это можно делать с помощью обычных элементов языка [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Поскольку запросы составляются на языке [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], их результаты возвращаются в виде строго типизированных объектов. Эти объекты поддерживают технологию IntelliSense, что позволяет писать код быстрее и перехватывать ошибки в запросах при компиляции, а не при выполнении. Запросы LINQ можно использовать как источник дополнительных запросов для уточнения результатов, а также связывать с элементами управления, позволяя пользователям легко просматривать и изменять результаты запросов.  
  
 Например в следующем примере кода показан запрос LINQ, возвращающий список заказчиков из коллекции и группирующий их по расположению.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
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
  
-   [Как и пошаговые руководства](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a>Выполнение примеров  
 Для выполнения примеров, приведенных во введении и в разделе «Структура запроса LINQ», используйте указанный ниже код, который возвращает список клиентов и заказов.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
##  <a name="LINQProviders"></a>Поставщики LINQ  
 Объект *поставщика LINQ* сопоставляет ваш [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] запросы LINQ для запрашиваемым источником данных. При написании запроса LINQ поставщик принимает запрос и переводит его в команды, которые источник данных будет способен выполнить. Затем поставщик преобразует данные из источника в объекты, составляющие результат запроса. И, наконец, при отправке обновлений на источник данных он преобразует объекты в данные.  
  
 В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] входят следующие поставщики LINQ:  
  
|Поставщик|Описание|  
|---|---|  
|LINQ to Objects|Поставщик LINQ to Objects позволяет направлять запросы к коллекциям и массивам, которые находятся в памяти. Если объект поддерживает интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>, поставщик LINQ to Objects позволяет направлять к нему запросы.<br /><br /> Поставщик LINQ to Objects включается при импорте пространства имен <xref:System.Linq>, которое импортируется по умолчанию для всех проектов [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].<br /><br /> Дополнительные сведения о поставщик LINQ to Objects см. в разделе [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).|  
|LINQ to SQL|Поставщик LINQ to SQL позволяет запрашивать и изменять данные в базе данных SQL Server. Это упрощает сопоставление объектной модели приложения с таблицами и объектами в базе данных.<br /><br /> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] упрощает работу с LINQ to SQL включением реляционного конструктора объектов (O/R-конструктора). Он используется для создания в приложении модели объекта, которая сопоставляется с объектами в базе данных. Реляционный конструктор объектов также предоставляет функциональные возможности сопоставления сохраненных процедур и функций <xref:System.Data.Linq.DataContext> объекта, который управляет связью с базой данных и сохраняет состояние для проверки оптимистического параллелизма.<br /><br /> Дополнительные сведения о поставщике LINQ to SQL см. в разделе [LINQ to SQL](https://msdn.microsoft.com/library/bb386976). Дополнительные сведения о реляционном конструкторе объектов см. в разделе [средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Поставщик LINQ to XML позволяет запрашивать и изменять XML. XML можно изменить в памяти, загрузить из файла и сохранить в файл.<br /><br /> Кроме того, поставщик LINQ to XML разрешает использовать литералы XML и свойств оси XML, что позволяет записывать XML непосредственно в код [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Поставщик LINQ to DataSet позволяет запрашивать и обновлять данные в [!INCLUDE[vstecado](~/includes/vstecado-md.md)] набора данных. Функции LINQ можно добавить в приложения, использующие наборы данных — это позволит упростить и расширить возможности составления запросов, статистической обработки и обновления данных в наборе данных.<br /><br /> Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
##  <a name="StructureOfALINQQuery"></a>Структура запроса LINQ  
 Запрос LINQ, часто называют *выражение запроса*, состоит из комбинации предложений запросов, определяющих источники данных и переменные итерации для запроса. Выражение запроса может также включать инструкции для сортировки, фильтрации, группировки и присоединения либо формулы для применения к исходным данным. Синтаксис выражения запроса напоминает синтаксис SQL, поэтому многие его элементы могут показаться вам знакомыми.  
  
 Выражение запроса начинается с предложения `From`. Это предложение определяет исходные данные для запроса и переменные, которые используются для обращения к каждому элементу источника данных по отдельности. Эти переменные называются *переменные диапазона* или *переменные итераций*. Предложение `From` является обязательным для запросов, кроме запросов `Aggregate`, где предложение `From` использовать необязательно. После определения области и источника запроса в предложении `From` или `Aggregate` можно добавить любую комбинацию предложений для уточнения запроса. Дополнительные сведения о предложениях запросов см. в разделе «Операторы запросов LINQ [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]» далее в этом разделе. Например, следующий запрос определяет исходную коллекцию данных клиента как переменную `customers` и как итерационную переменную `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 Данный пример составляет допустимый запрос сам по себе, однако особенно эффективным запрос становится при добавлении нескольких предложений, уточняющих его результат. Например, предложение `Where` позволяет отфильтровать результат по одному или нескольким значениям. Каждое выражение запроса — это одна строка кода, так что предложения можно просто добавлять в конец запроса. Запрос можно разбить на несколько текстовых строк, чтобы сделать его более удобочитаемым. Для этого используется символ продолжения строки (_). В приведенном ниже примере кода показан пример запроса с предложением `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Другое эффективное предложение запроса — это предложение `Select`, которое позволяет возвращать из источника данных только избранные поля. Запросы LINQ возвращают перечислимые коллекции строго типизированных объектов. Запрос может вернуть коллекцию как анонимных, так и именованных типов. Предложение `Select` позволяет вернуть из источника данных отдельное поле. В этом случае типом возвращаемой коллекции является тип этого поля. Кроме того, предложение `Select` позволяет вернуть из источника данных несколько полей. В этом случае типом возвращаемой коллекции становится новый анонимный тип. Возвращенные запросом поля можно сопоставить с полями указанного именованного типа. В приведенном ниже примере кода показано выражение запроса, возвращающее коллекцию анонимных типов, члены которой заполняются данными из выбранных полей источника данных.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Запросы LINQ могут также использоваться для объединения нескольких источников данных и получения единого результата. Это можно сделать с помощью одного или нескольких предложений `From` или с помощью предложений `Join` или `Group Join`. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов и возвращающее коллекцию анонимных типов, содержащих объединенные данные.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 Для получения иерархического результата, содержащего коллекцию объектов клиента, в запросе можно использовать предложение `Group Join`. Каждый объект клиента имеет свойство, содержащее коллекцию всех заказов этого клиента. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов в иерархический результат и возвращающее коллекцию анонимных типов. Запрос возвращает тип, у которого есть свойство `CustomerOrders`, содержащее коллекцию данных заказов клиента. У него также есть свойство `OrderTotal`, которое содержит общую сумму всех заказов этого клиента. (Этот запрос эквивалентен LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Имеется несколько дополнительных операторов запросов LINQ, которые можно использовать для создания эффективных выражений запросов. В следующем разделе описываются различные предложения запросов, которые можно использовать в выражениях запросов. Дополнительные сведения о [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предложения запроса см. в разделе [запросы](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a>Операторы запросов LINQ в Visual Basic  
 Классы в пространствах имен <xref:System.Linq> и других пространствах имен, поддерживающих запросы LINQ (в частности, System.Linq), содержат методы создания и уточнения запросов с учетом нужд приложения. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] содержит ключевые слова для наиболее распространенных предложений запросов, описанные в приведенной ниже таблице.  
  
|Термин|Определение|  
|---|---|  
|[Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md)|Запрос должен начинаться с предложения `From` или `Aggregate`. Предложение `From` определяет коллекцию источника и переменную итерации для запроса. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#7](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_8.vb)]|  
|[Предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md)|Необязательно. Объявляет набор переменных итераций для запроса. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#8](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_9.vb)]<br /><br /> Если предложение `Select` не указано, то переменные итераций для запроса состоят из переменных итераций, указанных предложением `From` или `Aggregate`.|  
|[Предложения Where](../../../../visual-basic/language-reference/queries/where-clause.md)|Необязательно. Определяет условие фильтрации для запроса. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#9](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_10.vb)]|  
|[Предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Необязательно. Определяет порядок сортировки для столбцов в запросе. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_11.vb)]|  
|[Предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md)|Необязательно. Объединяет две коллекции в одну. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_12.vb)]|  
|[Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Необязательно. Группирует элементы результата запроса. Может использоваться для применения агрегатных функций к каждой группе. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_13.vb)]|  
|[Предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Необязательно. Объединяет две коллекции в одну иерархическую коллекцию. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_14.vb)]|  
|[Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Запрос должен начинаться с предложения `From` или `Aggregate`. Предложение `Aggregate` применяет к коллекции одну или несколько агрегатных функций. Например, предложение `Aggregate` можно использовать для вычисления суммы всех возвращенных запросом элементов.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_15.vb)]<br /><br /> Предложение `Aggregate` можно также использовать для изменения запроса. Например, с помощью предложения `Aggregate` можно произвести вычисление с соответствующей коллекцией запросов.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_16.vb)]|  
|[Предложение Let](../../../../visual-basic/language-reference/queries/let-clause.md)|Необязательно. Вычисляет значение и присваивает его новой переменной в запросе. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_17.vb)]|  
|[Предложение Distinct](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Необязательно. Ограничивает значения текущей переменной итерации, чтобы исключить повторяющиеся значения в результатах запроса. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#17](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_18.vb)]|  
|[Предложение Skip](../../../../visual-basic/language-reference/queries/skip-clause.md)|Необязательно. Пропускает заданное число элементов в коллекции и возвращает остальные элементы. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#18](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_19.vb)]|  
|[Предложение Skip While](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Необязательно. Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#19](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_20.vb)]|  
|[Предложение Take](../../../../visual-basic/language-reference/queries/take-clause.md)|Необязательно. Возвращает указанное число идущих подряд элементов с начала коллекции. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#20](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_21.vb)]|  
|[Предложение Take While](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Необязательно. Включает элементы в коллекцию, если заданное условие имеет значение `true`, и пропускает остальные элементы. Пример:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#21](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_22.vb)]|  
  
 Дополнительные сведения о [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предложения запроса см. в разделе [запросы](../../../../visual-basic/language-reference/queries/queries.md).  
  
 Обращаясь к членам перечислимых и доступных для запроса типов, предоставляемых технологией LINQ, можно использовать дополнительные возможности запросов LINQ. Для этого на результат выражения запроса необходимо вызвать определенный оператор запроса. Например, в приведенном ниже примере кода применяется метод <xref:System.Linq.Enumerable.Union%2A>, позволяющий объединить результаты двух запросов в один. Для возвращения результата запроса в виде универсального списка используется метод <xref:System.Linq.Enumerable.ToList%2A>.  
  
 [!code-vb[VbVbalrIntroToLINQ#22](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Дополнительные сведения о дополнительных возможностях LINQ см. в разделе [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
##  <a name="ConnectingToADatabase"></a>Подключение к базе данных с помощью LINQ to SQL  
 В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для идентификации объектов базы данных SQL Server (таблиц, представлений и хранимых процедур), к которым необходимо получить доступ, используется файл LINQ to SQL. Файл LINQ to SQL имеет расширение DBML.  
  
 При наличии допустимое подключение к базе данных SQL Server, можно добавить **LINQ to SQL Classes** шаблона элемента в проект. Это позволит отобразить реляционный конструктор объектов (O/R-конструктор). O/R-конструктор дает возможность перетаскивать элементы, которые нужно получить доступ в коде, из **обозревателя серверов**/**обозреватель баз данных** на поверхность конструктора. Файл LINQ to SQL добавляет в проект объект <xref:System.Data.Linq.DataContext>. Этот объект включает свойства и коллекции для таблиц и представлений, к которым нужно получить доступ, а также необходимые методы для хранимых процедур. После сохранения изменений в файле LINQ to SQL (DBML) можно получить доступ к этим объектам в коде, обратившись к определенному O/R-конструктором объекту <xref:System.Data.Linq.DataContext>. Объекту <xref:System.Data.Linq.DataContext> для проекта присваивается имя, которое определяется именем файла LINQ to SQL. Например, файл LINQ to SQL с именем Northwind.dbml создаст объект <xref:System.Data.Linq.DataContext> с именем `NorthwindDataContext`.  
  
 Примеры с пошаговыми инструкциями см. в разделе [как: запрос к базе данных](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) и [как: вызов хранимой процедуры](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a>Возможности Visual Basic, поддерживающие LINQ  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] включает и другие возможности, упрощающие работу с технологией LINQ и уменьшающие размер кода, необходимый для выполнения запросов LINQ. В число этих требований входят следующие:  
  
-   **Анонимные типы**, что позволяет создать новый тип на основе результата запроса.  
  
-   **Неявно типизированные переменные**, позволяющие отложить Указание типа и позволить компилятору передавать тип, основанный на результатах запроса.  
  
-   **Методы расширения**, позволяющие расширять существующий тип своими собственными методами без изменения самого типа.  
  
 Дополнительные сведения см. в разделе [Visual Basic возможности, поддержка LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a>Отложенное и немедленное выполнение запроса  
 Процессы выполнения и создания запросов разделены. После создания запроса его выполнение инициируется отдельным механизмом. Запрос может выполняться, как только она определена (*немедленное выполнение*), или его определение может быть сохранено и запрос может быть выполнен позднее (*отложенного выполнения*).  
  
 По умолчанию вновь созданный запрос автоматически не выполняется. Вместо этого определение запроса сохраняется в переменной, которая используется для ссылки на результат этого запроса. Если впоследствии код обращается к переменной результата запроса, например в рамках цикла `For…Next`, запрос выполняется. Этот процесс называется *отложенного выполнения*.  
  
 Запросы также могут быть выполнены, когда они уже определены, которые называют *немедленное выполнение*. Немедленное выполнение можно инициировать с помощью метода, который требует доступа к отдельным элементам результата запроса. Это может быть результатом использования агрегатных функций, таких как `Count`, `Sum`, `Average`, `Min` или `Max`. Дополнительные сведения об агрегатных функциях см. в разделе [предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Принудительно вызвать немедленное выполнение запросов позволяют также методы `ToList` и `ToArray`. Это пригодится в том случае, если требуется выполнить запрос немедленно и кэшировать результаты. Дополнительные сведения об этих методах см. в разделе [преобразование типов данных](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Дополнительные сведения о выполнении запроса см. в разделе [написание вашего первого запроса LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a>XML в Visual Basic  
 Возможности XML в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] включают литералы XML и свойства оси XML, что позволяет легко создать, использовать, запрашивать и изменять XML в коде. Литералы XML позволяют записывать XML непосредственно в код. Компилятор Visual Basic обрабатывает XML как объект данных первого класса.  
  
 В приведенном ниже примере кода показано, как создать элемент XML, получить доступ к его дочерним элементам и атрибутам и сделать запросы к содержимому элемента с помощью LINQ.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a>Связанные ресурсы  
  
|Раздел|Описание|  
|---|---|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Описание возможностей XML в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], к которым можно делать запросы и которые позволяют включать XML в код [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] как объекты данных первого класса.|  
|[Запросы](../../../../visual-basic/language-reference/queries/queries.md)|Содержит справочные сведения о предложениях запросов, которые доступны в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].|  
|[Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ.|  
|[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to SQL.|  
|[LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to Objects.|  
|[LINQ to ADO.NET (Страница портала)](http://msdn.microsoft.com/library/dd7d3c6a-ff98-47e9-a1a7-2d4cfc42d150)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to [!INCLUDE[vstecado](~/includes/vstecado-md.md)].|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a>Как и пошаговые руководства  
 [How to: Query a Database](how-to-query-a-database-by-using-linq.md) (Практическое руководство. Выполнение запросов к базе данных)  
  
 [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md) (Практическое руководство. Вызов хранимой процедуры)  
  
 [How to: Modify Data in a Database](how-to-modify-data-in-a-database-by-using-linq.md) (Практическое руководство. Изменение данных в базе данных)  
  
 [How to: Combine Data with Joins](how-to-combine-data-with-linq-by-using-joins.md) (Практическое руководство. Объединение данных с помощью соединений)  
  
 [How to: Sort Query Results](how-to-sort-query-results-by-using-linq.md) (Практическое руководство. Сортировка результатов запроса)  
  
 [How to: Filter Query Results](how-to-filter-query-results-by-using-linq.md) (Практическое руководство. Фильтрование результатов запроса)  
  
 [How to: Count, Sum, or Average Data](how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)  
  
 [How to: Find the Minimum or Maximum Value in a Query Result](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)  
  
 [Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)  
  
## <a name="featured-book-chapters"></a>Главы в популярных книгах  
 [Глава 17: LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) в [программирования Visual Basic 2008](http://go.microsoft.com/fwlink/?LinkId=195383)  
  
## <a name="see-also"></a>См. также  
 [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 [LINQ to DataSet Обзор](../../../../framework/data/adonet/linq-to-dataset-overview.md)  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
 [Средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
 [Методы DataContext (O/R-конструктор)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
