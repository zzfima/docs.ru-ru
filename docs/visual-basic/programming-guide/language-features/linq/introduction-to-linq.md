---
title: Знакомство с LINQ в Visual Basic
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
ms.openlocfilehash: f5222d51ff2f60dd31ec52a8d5d6d52f37e02443
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739206"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Знакомство с LINQ в Visual Basic
Добавляет возможности запросов в Visual Basic Language-Integrated Query (LINQ) и предоставляет простые и мощные возможности при работе с любыми видами данных. Вместо отправки запроса к базе данных должны быть обработаны или работы с отдельный синтаксис запросов для каждого типа данных, которую нужно найти, LINQ представляет запросы как часть языка Visual Basic. Синтаксис запросов не зависит от типа данных.  
  
 LINQ позволяет запрашивать данные из базы данных SQL Server, XML, в памяти массивов и коллекций, наборы данных ADO.NET или удаленным или локальным источником данных, поддерживающий LINQ. Все это делается с помощью Общие элементы языка Visual Basic. Поскольку запросы пишутся на языке Visual Basic, результаты запроса возвращаются в виде строго типизированных объектов. Эти объекты поддерживают технологию IntelliSense, что позволяет писать код быстрее и перехватывать ошибки в запросах при компиляции, а не при выполнении. Запросы LINQ можно использовать как источник дополнительных запросов для уточнения результатов, а также связывать с элементами управления, позволяя пользователям легко просматривать и изменять результаты запросов.  
  
 Например в следующем примере кода показан запрос LINQ, возвращающий список заказчиков из коллекции и группирующий их по расположению.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
## <a name="running-the-examples"></a>Выполнение примеров  
 Для запуска примеров во введении и в [структура запроса LINQ](#structure-of-a-linq-query) разделе, включают следующий код, который возвращает список клиентов и заказов.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
## <a name="linq-providers"></a>Поставщики LINQ  
 Объект *поставщик LINQ* сопоставляет запросы LINQ в Visual Basic с запрашиваемым источником данных. При написании запроса LINQ поставщик принимает запрос и переводит его в команды, которые источник данных будет способен выполнить. Затем поставщик преобразует данные из источника в объекты, составляющие результат запроса. И, наконец, при отправке обновлений на источник данных он преобразует объекты в данные.  
  
 Visual Basic включает в себя следующие поставщики LINQ.  
  
|Поставщик|Описание:|  
|---|---|  
|LINQ to Objects|Поставщик LINQ to Objects позволяет направлять запросы к коллекциям и массивам, которые находятся в памяти. Если объект поддерживает интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>, поставщик LINQ to Objects позволяет направлять к нему запросы.<br /><br /> Вы можете включить поставщик LINQ to Objects, импортировав <xref:System.Linq> пространство имен, которое импортируется по умолчанию для всех проектов Visual Basic.<br /><br /> Дополнительные сведения о поставщике LINQ to Objects, см. в разделе [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Поставщик LINQ to SQL позволяет запрашивать и изменять данные в базе данных SQL Server. Это упрощает сопоставление объектной модели приложения с таблицами и объектами в базе данных.<br /><br /> Visual Basic упрощает работу с LINQ to SQL включением реляционный конструктор объектов (O/R Designer). Он используется для создания в приложении модели объекта, которая сопоставляется с объектами в базе данных. Реляционный конструктор объектов также предоставляет функциональные возможности сопоставления сохраненных процедур и функций <xref:System.Data.Linq.DataContext> объект, который управляет связью с базой данных и сохраняет состояние проверок на оптимистический параллелизм.<br /><br /> Дополнительные сведения о поставщике LINQ to SQL, см. в разделе [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Дополнительные сведения о реляционном конструкторе объектов см. в разделе [средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Поставщик LINQ to XML позволяет запрашивать и изменять XML. XML можно изменить в памяти, загрузить из файла и сохранить в файл.<br /><br /> Кроме того, поставщик LINQ to XML разрешает литералы XML и свойства оси XML, которые позволяют записывать XML непосредственно в код Visual Basic. Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Поставщик LINQ to DataSet позволяет запрашивать и обновлять данные в [!INCLUDE[vstecado](~/includes/vstecado-md.md)] набора данных. Функции LINQ можно добавить в приложения, использующие наборы данных — это позволит упростить и расширить возможности составления запросов, статистической обработки и обновления данных в наборе данных.<br /><br /> Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Структура запроса LINQ  
 Запрос LINQ, часто называют *выражение запроса*, состоит из комбинации предложений запросов, определяющих источники данных и переменные итерации для запроса. Выражение запроса может также включать инструкции для сортировки, фильтрации, группировки и присоединения либо формулы для применения к исходным данным. Синтаксис выражения запроса напоминает синтаксис SQL, поэтому многие его элементы могут показаться вам знакомыми.  
  
 Выражение запроса начинается с предложения `From`. Это предложение определяет исходные данные для запроса и переменные, которые используются для обращения к каждому элементу источника данных по отдельности. Эти переменные называются *переменные диапазона* или *переменные итерации*. Предложение `From` является обязательным для запросов, кроме запросов `Aggregate`, где предложение `From` использовать необязательно. После определения области и источника запроса в предложении `From` или `Aggregate` можно добавить любую комбинацию предложений для уточнения запроса. Сведения о предложениях запросов см. в разделе операторов запросов LINQ в Visual Basic далее в этом разделе. Например, следующий запрос определяет исходную коллекцию данных клиента как переменную `customers` и как итерационную переменную `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 Данный пример составляет допустимый запрос сам по себе, однако особенно эффективным запрос становится при добавлении нескольких предложений, уточняющих его результат. Например, предложение `Where` позволяет отфильтровать результат по одному или нескольким значениям. Каждое выражение запроса — это одна строка кода, так что предложения можно просто добавлять в конец запроса. Запрос можно разбить на несколько строк текста для улучшения читаемости с помощью символ подчеркивания (\_) символ продолжения строки. В приведенном ниже примере кода показан пример запроса с предложением `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Другое эффективное предложение запроса — это предложение `Select`, которое позволяет возвращать из источника данных только избранные поля. Запросы LINQ возвращают перечислимые коллекции строго типизированных объектов. Запрос может вернуть коллекцию как анонимных, так и именованных типов. Предложение `Select` позволяет вернуть из источника данных отдельное поле. В этом случае типом возвращаемой коллекции является тип этого поля. Кроме того, предложение `Select` позволяет вернуть из источника данных несколько полей. В этом случае типом возвращаемой коллекции становится новый анонимный тип. Возвращенные запросом поля можно сопоставить с полями указанного именованного типа. В приведенном ниже примере кода показано выражение запроса, возвращающее коллекцию анонимных типов, члены которой заполняются данными из выбранных полей источника данных.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Запросы LINQ могут также использоваться для объединения нескольких источников данных и получения единого результата. Это можно сделать с помощью одного или нескольких предложений `From` или с помощью предложений `Join` или `Group Join`. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов и возвращающее коллекцию анонимных типов, содержащих объединенные данные.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 Для получения иерархического результата, содержащего коллекцию объектов клиента, в запросе можно использовать предложение `Group Join`. Каждый объект клиента имеет свойство, содержащее коллекцию всех заказов этого клиента. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов в иерархический результат и возвращающее коллекцию анонимных типов. Запрос возвращает тип, у которого есть свойство `CustomerOrders`, содержащее коллекцию данных заказов клиента. У него также есть свойство `OrderTotal`, которое содержит общую сумму всех заказов этого клиента. (Этот запрос эквивалентен LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Имеется несколько дополнительных операторов запросов LINQ, которые можно использовать для создания эффективных выражений запросов. В следующем разделе описываются различные предложения запросов, которые можно использовать в выражениях запросов. Сведения о предложениях запросов в Visual Basic, см. в разделе [запросы](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Операторы запросов LINQ в Visual Basic  

Классы в пространствах имен <xref:System.Linq> и других пространствах имен, поддерживающих запросы LINQ (в частности, System.Linq), содержат методы создания и уточнения запросов с учетом нужд приложения. Visual Basic содержит ключевые слова для следующих распространенных предложений запросов. Сведения о предложениях запросов в Visual Basic, см. в разделе [запросы](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Предложение From

Либо [ `From` предложение](../../../../visual-basic/language-reference/queries/from-clause.md) или `Aggregate` предложение необходимо для начала запроса. Предложение `From` определяет коллекцию источника и переменную итерации для запроса. Пример:

[!code-vb[VbVbalrIntroToLINQ#7](codesnippet/VisualBasic/introduction-to-linq_8.vb)]

### <a name="select-clause"></a>Select - предложение

Необязательный параметр. Объект [ `Select` предложение](../../../../visual-basic/language-reference/queries/select-clause.md) объявляет набор переменных итераций для запроса. Пример:

[!code-vb[VbVbalrIntroToLINQ#8](codesnippet/VisualBasic/introduction-to-linq_9.vb)]

Если предложение `Select` не указано, то переменные итераций для запроса состоят из переменных итераций, указанных предложением `From` или `Aggregate`.

### <a name="where-clause"></a>Предложение Where

Необязательный параметр. Объект [ `Where` предложение](../../../../visual-basic/language-reference/queries/where-clause.md) определяет условие фильтрации для запроса. Пример:

[!code-vb[VbVbalrIntroToLINQ#9](codesnippet/VisualBasic/introduction-to-linq_10.vb)]

### <a name="order-by-clause"></a>Предложение Order By]

| Необязательно. [ `Order By` Предложение](../../../../visual-basic/language-reference/queries/order-by-clause.md) определяет порядок сортировки для столбцов в запросе. Пример:

[!code-vb[VbVbalrIntroToLINQ#10](codesnippet/VisualBasic/introduction-to-linq_11.vb)]

### <a name="join-clause"></a>Join - предложение

Необязательный параметр. Объект [ `Join` предложение](../../../../visual-basic/language-reference/queries/join-clause.md) объединяет две коллекции в одну коллекцию. Пример:

[!code-vb[VbVbalrIntroToLINQ#11](codesnippet/VisualBasic/introduction-to-linq_12.vb)]

### <a name="group-by-clause"></a>Group By - предложение

Необязательный параметр. Объект [ `Group By` предложение](../../../../visual-basic/language-reference/queries/group-by-clause.md) группирует элементы результата запроса. Его можно использовать для применения агрегатных функций к каждой группе. Пример:

[!code-vb[VbVbalrIntroToLINQ#12](codesnippet/VisualBasic/introduction-to-linq_13.vb)]

### <a name="group-join-clause"></a>Group Join - предложение

Необязательный параметр. Объект [ `Group Join` предложение](../../../../visual-basic/language-reference/queries/group-join-clause.md) объединяет две коллекции в одну иерархическую коллекцию. Пример:

[!code-vb[VbVbalrIntroToLINQ#13](codesnippet/VisualBasic/introduction-to-linq_14.vb)]

### <a name="aggregate-clause"></a>Aggregate - предложение

Либо [ `Aggregate` предложение](../../../../visual-basic/language-reference/queries/aggregate-clause.md) или `From` предложение необходимо для начала запроса. Предложение `Aggregate` применяет к коллекции одну или несколько агрегатных функций. Например, можно использовать `Aggregate` предложение для вычисления суммы всех элементов, возвращаемых запросом, как показано в следующем примере.

[!code-vb[VbVbalrIntroToLINQ#14](codesnippet/VisualBasic/introduction-to-linq_15.vb)]

Предложение `Aggregate` можно также использовать для изменения запроса. Например, с помощью предложения `Aggregate` можно произвести вычисление с соответствующей коллекцией запросов. Пример:

[!code-vb[VbVbalrIntroToLINQ#15](codesnippet/VisualBasic/introduction-to-linq_16.vb)]

### <a name="let-clause"></a>Let - предложение

Необязательный параметр. Объект [ `Let` предложение](../../../../visual-basic/language-reference/queries/let-clause.md) вычисляет значение и присваивает его новой переменной в запросе. Пример:

[!code-vb[VbVbalrIntroToLINQ#16](codesnippet/VisualBasic/introduction-to-linq_17.vb)]

### <a name="distinct-clause"></a>Distinct - предложение

Необязательный параметр. Объект `Distinct` предложение ограничивает значения текущей переменной итерации, чтобы исключить повторяющиеся значения в результатах запроса. Пример:

[!code-vb[VbVbalrIntroToLINQ#17](codesnippet/VisualBasic/introduction-to-linq_18.vb)]

### <a name="skip-clause"></a>Skip - предложение

Необязательный параметр. Объект [ `Skip` предложение](../../../../visual-basic/language-reference/queries/skip-clause.md) пропускает указанное число элементов в коллекции и возвращает остальные элементы. Пример:

[!code-vb[VbVbalrIntroToLINQ#18](codesnippet/VisualBasic/introduction-to-linq_19.vb)]

### <a name="skip-while-clause"></a>Skip While - предложение

Необязательный параметр. Объект [ `Skip While` предложение](../../../../visual-basic/language-reference/queries/skip-while-clause.md) пропускает элементы в коллекции, до тех пор, пока заданное условие имеет `true` и затем возвращает оставшиеся элементы. Пример:

[!code-vb[VbVbalrIntroToLINQ#19](codesnippet/VisualBasic/introduction-to-linq_20.vb)]

### <a name="take-clause"></a>Take - предложение

Необязательный параметр. Объект [ `Take` предложение](../../../../visual-basic/language-reference/queries/take-clause.md) возвращает указанное число идущих подряд элементов с начала коллекции. Пример:

[!code-vb[VbVbalrIntroToLINQ#20](codesnippet/VisualBasic/introduction-to-linq_21.vb)]

### <a name="take-while-clause"></a>Take While - предложение

Необязательный параметр. Объект [ `Take While` предложение](../../../../visual-basic/language-reference/queries/take-while-clause.md) включает элементы в коллекции до тех пор, пока заданное условие имеет `true` и пропускает остальные элементы. Пример:

[!code-vb[VbVbalrIntroToLINQ#21](codesnippet/VisualBasic/introduction-to-linq_22.vb)]
  
## <a name="use-additional-linq-query-features"></a>Использовать дополнительные возможности запросов LINQ  
  
Обращаясь к членам перечислимых и доступных для запроса типов, предоставляемых технологией LINQ, можно использовать дополнительные возможности запросов LINQ. Для этого на результат выражения запроса необходимо вызвать определенный оператор запроса. Например, в следующем примере используется <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> метод, чтобы объединить результаты двух запросов в один. Для возвращения результата запроса в виде универсального списка используется метод <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>.
  
 [!code-vb[VbVbalrIntroToLINQ#22](codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Дополнительные сведения о дополнительных возможностях LINQ см. в разделе [Общие сведения о стандартных операторах запроса](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Соединиться с базой данных с помощью LINQ to SQL  
 В Visual Basic идентификации объектов базы данных SQL Server, таких как таблицы, представления и хранимые процедуры, которые необходимо получить доступ с помощью LINQ to SQL-файл. Файл LINQ to SQL имеет расширение DBML.  
  
 При наличии допустимое соединение с базой данных SQL Server, вы можете добавить **LINQ to SQL Classes** шаблона элемента в проект. Это позволит отобразить реляционный конструктор объектов (O/R-конструктор). O/R-конструктор дает возможность перетаскивать элементы, которые вы хотите получить доступ к в коде из **обозревателя серверов**/**обозреватель баз данных** в область конструктора. Файл LINQ to SQL добавляет в проект объект <xref:System.Data.Linq.DataContext>. Этот объект включает свойства и коллекции для таблиц и представлений, к которым нужно получить доступ, а также необходимые методы для хранимых процедур. После сохранения изменений в файле LINQ to SQL (DBML) можно получить доступ к этим объектам в коде, обратившись к определенному O/R-конструктором объекту <xref:System.Data.Linq.DataContext>. Объекту <xref:System.Data.Linq.DataContext> для проекта присваивается имя, которое определяется именем файла LINQ to SQL. Например, файл LINQ to SQL с именем Northwind.dbml создаст объект <xref:System.Data.Linq.DataContext> с именем `NorthwindDataContext`.  
  
 Примеры с пошаговыми инструкциями см. в разделе [как: Запрос к базе данных](how-to-query-a-database-by-using-linq.md) и [как: Вызовите хранимую процедуру](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Возможности Visual Basic, поддерживающие LINQ  
 Visual Basic включает и другие возможности, упрощающие использование LINQ и сократить объем кода, который необходимо написать для выполнения запросов LINQ. В число этих требований входят следующие:  
  
-   **Анонимные типы**, которые позволяют создать новый тип на основе результата запроса.  
  
-   **Неявно типизированные переменные**, позволяющие отложить Указание типа и позволить компилятору передавать тип на основе результатов запроса.  
  
-   **Методы расширения**, которые позволяют расширить существующий тип своими собственными методами без изменения самого типа.  
  
 Дополнительные сведения см. в разделе [функции, поддержка LINQ в Visual Basic](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Отложенное и немедленное выполнение запроса

 Процессы выполнения и создания запросов разделены. После создания запроса его выполнение инициируется отдельным механизмом. Возможность выполнения запросов, как только она определена (*немедленное выполнение*), или его определение может быть сохранено, и запрос будет выполнен позже (*отложенное выполнение*).  
  
 По умолчанию вновь созданный запрос автоматически не выполняется. Вместо этого определение запроса сохраняется в переменной, которая используется для ссылки на результат этого запроса. Если впоследствии код обращается к переменной результата запроса, например в рамках цикла `For…Next`, запрос выполняется. Этот процесс называется *отложенного выполнения*.  
  
 Запросы также могут быть выполнены, когда они определены, которые называются *немедленное выполнение*. Немедленное выполнение можно инициировать с помощью метода, который требует доступа к отдельным элементам результата запроса. Это может быть результатом использования агрегатных функций, таких как `Count`, `Sum`, `Average`, `Min` или `Max`. Дополнительные сведения об агрегатных функциях см. в разделе [предложение Aggregate](../../../language-reference/queries/aggregate-clause.md).  
  
 Принудительно вызвать немедленное выполнение запросов позволяют также методы `ToList` и `ToArray`. Это пригодится в том случае, если требуется выполнить запрос немедленно и кэшировать результаты. Дополнительные сведения об этих методах см. в разделе [преобразование типов данных](../../concepts/linq/converting-data-types.md).  
  
 Дополнительные сведения о выполнении запросов см. в разделе [Your первого запроса LINQ записи](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML в Visual Basic  
 Свойства XML в Visual Basic включают литералы XML и свойства оси XML, которые позволяют легко создавать, доступ, запрашивать и изменять XML в коде. Литералы XML позволяют записывать XML непосредственно в код. Компилятор Visual Basic обрабатывает XML как объект данных первого класса.  
  
 В приведенном ниже примере кода показано, как создать элемент XML, получить доступ к его дочерним элементам и атрибутам и сделать запросы к содержимому элемента с помощью LINQ.  
  
 [!code-vb[VbXmlSamples#8](../../../language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Дополнительные сведения см. в разделе [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Связанные ресурсы  
  
|Раздел|Описание:|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Описание возможностей XML в Visual Basic, который может запрашиваться и, которые позволяют включать XML как объекты данных первого класса в коде Visual Basic.|  
|[Запросы](../../../language-reference/queries/index.md)|Содержит справочные сведения о предложениях запросов, которые доступны в Visual Basic.|  
|[Встроенный язык запросов LINQ](../../concepts/linq/index.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ.|  
|[LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to Objects.|  
|[LINQ to ADO.NET (Страница портала)](../../concepts/linq/linq-to-adonet-portal-page.md)|Содержит ссылки на общие сведения, рекомендации по программированию и примеры для LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Как и пошаговые руководства
 [Практическое руководство. Запрос к базе данных](how-to-query-a-database-by-using-linq.md)  
  
 [Практическое руководство. Вызов хранимой процедуры](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Практическое руководство. Изменение данных в базе данных](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Практическое руководство. Объединение данных с соединениями](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Практическое руководство. Сортировка результатов запроса](how-to-sort-query-results-by-using-linq.md)  
  
 [Практическое руководство. Фильтрование результатов запроса](how-to-filter-query-results-by-using-linq.md)  
  
 [Практическое руководство. Число, суммы или среднего значения данных](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Практическое руководство. Поиск минимального или максимального значения в результатах запроса](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Главы в популярных книгах  
 [Глава 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) в [программирования Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>См. также

- [Встроенный язык запросов LINQ](../../concepts/linq/index.md)
- [Общие сведения о LINQ to XML в Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Общие сведения о LINQ to DataSet](~/docs/framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)
- [Средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
