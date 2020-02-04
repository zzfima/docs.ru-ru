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
ms.openlocfilehash: 3f58edf326ab9415d78d7065d74d8c1954fbbf37
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "76315867"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Знакомство с LINQ в Visual Basic
Языковой интегрированный запрос (LINQ) добавляет возможности запросов в Visual Basic и предоставляет простые и эффективные возможности при работе со всеми типами данных. Вместо отправки запроса в базу данных для обработки или работы с другим синтаксисом запросов для каждого типа искомых данных LINQ вводит запросы в составе языка Visual Basic. Синтаксис запросов не зависит от типа данных.  
  
 LINQ позволяет запрашивать данные из SQL Server базы данных, XML, массивов в памяти и коллекций, ADO.NET DataSets или любого другого удаленного или локального источника данных, поддерживающего LINQ. Все это можно сделать с помощью стандартных элементов языка Visual Basic. Так как запросы написаны на языке Visual Basic, результаты запроса возвращаются в виде строго типизированных объектов. Эти объекты поддерживают технологию IntelliSense, что позволяет писать код быстрее и перехватывать ошибки в запросах при компиляции, а не при выполнении. Запросы LINQ можно использовать как источник дополнительных запросов для уточнения результатов, а также связывать с элементами управления, позволяя пользователям легко просматривать и изменять результаты запросов.  
  
 Например в следующем примере кода показан запрос LINQ, возвращающий список заказчиков из коллекции и группирующий их по расположению.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Выполнение примеров  
 Чтобы выполнить примеры во введении и в структуре раздела [запроса LINQ](#structure-of-a-linq-query) , включите следующий код, который возвращает списки клиентов и заказов.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>Поставщики LINQ  
 *Поставщик LINQ* сопоставляет Visual Basic запросы LINQ с запрашиваемым источником данных. При написании запроса LINQ поставщик принимает запрос и переводит его в команды, которые источник данных будет способен выполнить. Затем поставщик преобразует данные из источника в объекты, составляющие результат запроса. И, наконец, при отправке обновлений на источник данных он преобразует объекты в данные.  
  
 Visual Basic включает следующие поставщики LINQ.  
  
|Поставщик|Описание|  
|---|---|  
|LINQ to Objects|Поставщик LINQ to Objects позволяет направлять запросы к коллекциям и массивам, которые находятся в памяти. Если объект поддерживает интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>, поставщик LINQ to Objects позволяет направлять к нему запросы.<br /><br /> Поставщик LINQ to Objects можно включить, импортировав <xref:System.Linq> пространство имен, которое по умолчанию импортируется для всех проектов Visual Basic.<br /><br /> Дополнительные сведения о поставщике LINQ to Objects см. в разделе [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Поставщик LINQ to SQL позволяет запрашивать и изменять данные в базе данных SQL Server. Это упрощает сопоставление объектной модели приложения с таблицами и объектами в базе данных.<br /><br /> Visual Basic упрощает работу с LINQ to SQL, включая реляционный конструктор объектов (реляционный конструктор R). Он используется для создания в приложении модели объекта, которая сопоставляется с объектами в базе данных. Реляционный конструктор объектов также предоставляет функции для соотнесения хранимых процедур и функций к объекту <xref:System.Data.Linq.DataContext>, который управляет связью с базой данных и сохраняет состояние для проверок оптимистического параллелизма.<br /><br /> Дополнительные сведения о поставщике LINQ to SQL см. в разделе [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Дополнительные сведения о реляционный конструктор объектов см. в разделе [средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Поставщик LINQ to XML позволяет запрашивать и изменять XML. XML можно изменить в памяти, загрузить из файла и сохранить в файл.<br /><br /> Кроме того, поставщик LINQ to XML включает XML-литералы и свойства осей XML, позволяющие писать XML-код непосредственно в коде Visual Basic. Дополнительные сведения см. в разделе [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Поставщик LINQ to DataSet позволяет запрашивать и обновлять данные в наборе данных ADO.NET. Функции LINQ можно добавить в приложения, использующие наборы данных — это позволит упростить и расширить возможности составления запросов, статистической обработки и обновления данных в наборе данных.<br /><br /> Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Структура запроса LINQ  
 Запрос LINQ, часто называемый *выражением запроса*, состоит из сочетания предложений запроса, которые указывают источники данных и переменные итерации для запроса. Выражение запроса может также включать инструкции для сортировки, фильтрации, группировки и присоединения либо формулы для применения к исходным данным. Синтаксис выражения запроса напоминает синтаксис SQL, поэтому многие его элементы могут показаться вам знакомыми.  
  
 Выражение запроса начинается с предложения `From`. Это предложение определяет исходные данные для запроса и переменные, которые используются для обращения к каждому элементу источника данных по отдельности. Эти переменные являются именованными *переменными диапазона* или *переменными итераций*. Предложение `From` является обязательным для запросов, кроме запросов `Aggregate`, где предложение `From` использовать необязательно. После определения области и источника запроса в предложении `From` или `Aggregate` можно добавить любую комбинацию предложений для уточнения запроса. Дополнительные сведения о предложениях запросов см. в разделе Visual Basic операторы запросов LINQ далее в этой статье. Например, следующий запрос определяет исходную коллекцию данных клиента как переменную `customers` и как итерационную переменную `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Данный пример составляет допустимый запрос сам по себе, однако особенно эффективным запрос становится при добавлении нескольких предложений, уточняющих его результат. Например, предложение `Where` позволяет отфильтровать результат по одному или нескольким значениям. Каждое выражение запроса — это одна строка кода, так что предложения можно просто добавлять в конец запроса. Можно разбить запрос на несколько строк текста, чтобы улучшить удобочитаемость с помощью символа продолжения строки подчеркивания (\_). В приведенном ниже примере кода показан пример запроса с предложением `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Другое эффективное предложение запроса — это предложение `Select`, которое позволяет возвращать из источника данных только избранные поля. Запросы LINQ возвращают перечислимые коллекции строго типизированных объектов. Запрос может вернуть коллекцию как анонимных, так и именованных типов. Предложение `Select` позволяет вернуть из источника данных отдельное поле. В этом случае типом возвращаемой коллекции является тип этого поля. Кроме того, предложение `Select` позволяет вернуть из источника данных несколько полей. В этом случае типом возвращаемой коллекции становится новый анонимный тип. Возвращенные запросом поля можно сопоставить с полями указанного именованного типа. В приведенном ниже примере кода показано выражение запроса, возвращающее коллекцию анонимных типов, члены которой заполняются данными из выбранных полей источника данных.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Запросы LINQ могут также использоваться для объединения нескольких источников данных и получения единого результата. Это можно сделать с помощью одного или нескольких предложений `From` или с помощью предложений `Join` или `Group Join`. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов и возвращающее коллекцию анонимных типов, содержащих объединенные данные.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Для получения иерархического результата, содержащего коллекцию объектов клиента, в запросе можно использовать предложение `Group Join`. Каждый объект клиента имеет свойство, содержащее коллекцию всех заказов этого клиента. В приведенном ниже примере кода показано выражение запроса, объединяющее данные клиентов и заказов в иерархический результат и возвращающее коллекцию анонимных типов. Запрос возвращает тип, у которого есть свойство `CustomerOrders`, содержащее коллекцию данных заказов клиента. У него также есть свойство `OrderTotal`, которое содержит общую сумму всех заказов этого клиента. (Этот запрос эквивалентен LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Имеется несколько дополнительных операторов запросов LINQ, которые можно использовать для создания эффективных выражений запросов. В следующем разделе описываются различные предложения запросов, которые можно использовать в выражениях запросов. Дополнительные сведения о Visual Basic предложениях запросов см. в разделе [запросы](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic операторы запросов LINQ  

Классы в пространствах имен <xref:System.Linq> и других пространствах имен, поддерживающих запросы LINQ (в частности, System.Linq), содержат методы создания и уточнения запросов с учетом нужд приложения. Visual Basic содержит ключевые слова для следующих общих предложений запросов. Дополнительные сведения о Visual Basic предложениях запросов см. в разделе [запросы](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Предложение From

Для начала запроса требуется либо [предложение`From`](../../../../visual-basic/language-reference/queries/from-clause.md) , либо предложение `Aggregate`. Предложение `From` определяет коллекцию источника и переменную итерации для запроса. Например:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select - предложение

(Необязательный аргумент) [Предложение`Select`](../../../../visual-basic/language-reference/queries/select-clause.md) объявляет набор переменных итерации для запроса. Например:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Если предложение `Select` не указано, то переменные итераций для запроса состоят из переменных итераций, указанных предложением `From` или `Aggregate`.

### <a name="where-clause"></a>Предложение Where

(Необязательный аргумент) [Предложение`Where`](../../../../visual-basic/language-reference/queries/where-clause.md) задает условие фильтрации для запроса. Например:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By - предложение

(Необязательный аргумент) [Предложение`Order By`](../../../../visual-basic/language-reference/queries/order-by-clause.md) задает порядок сортировки для столбцов в запросе. Например:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join - предложение

(Необязательный аргумент) [Предложение`Join`](../../../../visual-basic/language-reference/queries/join-clause.md) объединяет две коллекции в одну. Например:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By - предложение

(Необязательный аргумент) [Предложение`Group By`](../../../../visual-basic/language-reference/queries/group-by-clause.md) группирует элементы результата запроса. Его можно использовать для применения агрегатных функций к каждой группе. Например:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join - предложение

(Необязательный аргумент) [Предложение`Group Join`](../../../../visual-basic/language-reference/queries/group-join-clause.md) объединяет две коллекции в одну иерархическую коллекцию. Например:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate - предложение

Для начала запроса требуется либо [предложение`Aggregate`](../../../../visual-basic/language-reference/queries/aggregate-clause.md) , либо предложение `From`. Предложение `Aggregate` применяет к коллекции одну или несколько агрегатных функций. Например, можно использовать предложение `Aggregate` для вычисления суммы всех элементов, возвращаемых запросом, как показано в следующем примере.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

Предложение `Aggregate` можно также использовать для изменения запроса. Например, с помощью предложения `Aggregate` можно произвести вычисление с соответствующей коллекцией запросов. Например:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let - предложение

(Необязательный аргумент) [Предложение`Let`](../../../../visual-basic/language-reference/queries/let-clause.md) выполняет вычисление значения и присваивает его новой переменной в запросе. Например:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct - предложение

(Необязательный аргумент) Предложение `Distinct` позволяет ограничивать значения текущей переменной итерации, чтобы исключить дублирующиеся значения в результатах запроса. Например:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip - предложение

(Необязательный аргумент) [Предложение`Skip`](../../../../visual-basic/language-reference/queries/skip-clause.md) обходит указанное число элементов в коллекции, а затем возвращает остальные элементы. Например:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While - предложение

(Необязательный аргумент) [Предложение`Skip While`](../../../../visual-basic/language-reference/queries/skip-while-clause.md) обходит элементы в коллекции, пока заданное условие `true`, а затем возвращает оставшиеся элементы. Например:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take - предложение

(Необязательный аргумент) [Предложение`Take`](../../../../visual-basic/language-reference/queries/take-clause.md) возвращает указанное число смежных элементов от начала коллекции. Например:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While - предложение

(Необязательный аргумент) [`Take While` предложение](../../../../visual-basic/language-reference/queries/take-while-clause.md) включает элементы в коллекцию, пока заданное условие `true` и обходит оставшиеся элементы. Например:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Использование дополнительных функций запросов LINQ  
  
Обращаясь к членам перечислимых и доступных для запроса типов, предоставляемых технологией LINQ, можно использовать дополнительные возможности запросов LINQ. Для этого на результат выражения запроса необходимо вызвать определенный оператор запроса. Например, в следующем примере используется метод <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> для объединения результатов двух запросов в один результат запроса. Для возвращения результата запроса в виде универсального списка используется метод <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 Дополнительные сведения о дополнительных возможностях LINQ см. в статье [Общие сведения о стандартных операторах запросов](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Подключение к базе данных с помощью LINQ to SQL  
 В Visual Basic вы определяете объекты базы данных SQL Server, такие как таблицы, представления и хранимые процедуры, к которым необходимо получить доступ с помощью файла LINQ to SQL. Файл LINQ to SQL имеет расширение DBML.  
  
 При наличии допустимого соединения с SQL Server базой данных можно добавить в проект шаблон элемента **LINQ to SQL классов** . Это позволит отобразить реляционный конструктор объектов (O/R-конструктор). Реляционный конструктор объектов позволяет перетаскивать элементы, к которым требуется доступ в коде, из **обозреватель сервера**/**Обозреватель базы данных** на поверхность конструктора. Файл LINQ to SQL добавляет в проект объект <xref:System.Data.Linq.DataContext>. Этот объект включает свойства и коллекции для таблиц и представлений, к которым нужно получить доступ, а также необходимые методы для хранимых процедур. После сохранения изменений в файле LINQ to SQL (DBML) можно получить доступ к этим объектам в коде, обратившись к определенному O/R-конструктором объекту <xref:System.Data.Linq.DataContext>. Объекту <xref:System.Data.Linq.DataContext> для проекта присваивается имя, которое определяется именем файла LINQ to SQL. Например, файл LINQ to SQL с именем Northwind.dbml создаст объект <xref:System.Data.Linq.DataContext> с именем `NorthwindDataContext`.  
  
 Примеры с пошаговыми инструкциями см. в разделе [как выполнить запрос к базе данных](how-to-query-a-database-by-using-linq.md) и [как вызвать хранимую процедуру](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic функции, поддерживающие LINQ  
 Visual Basic включает другие важные функции, которые делают использование LINQ простым и сокращают объем кода, который необходимо написать для выполнения запросов LINQ. К ним относятся следующие:  
  
- **Анонимные типы**, которые позволяют создать новый тип на основе результата запроса.  
  
- **Неявно типизированные переменные**, которые позволяют отложить указание типа и позволить компилятору определить тип на основе результата запроса.  
  
- **Методы расширения**, позволяющие расширить существующий тип собственными методами, не изменяя сам тип.  
  
 Дополнительные сведения см. в разделе [Visual Basic функции, поддерживающие LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Отложенное и немедленное выполнение запроса

 Процессы выполнения и создания запросов разделены. После создания запроса его выполнение инициируется отдельным механизмом. Запрос может быть выполнен, как только он определен (*немедленное выполнение*), либо можно сохранить определение, и запрос можно будет выполнить позже (*Отложенное выполнение*).  
  
 По умолчанию вновь созданный запрос автоматически не выполняется. Вместо этого определение запроса сохраняется в переменной, которая используется для ссылки на результат этого запроса. Если впоследствии код обращается к переменной результата запроса, например в рамках цикла `For…Next`, запрос выполняется. Этот процесс называется *отложенным выполнением*.  
  
 Запросы также можно выполнять, когда они определены, что называется *немедленной выполнением*. Немедленное выполнение можно инициировать с помощью метода, который требует доступа к отдельным элементам результата запроса. Это может быть результатом использования агрегатных функций, таких как `Count`, `Sum`, `Average`, `Min` или `Max`. Дополнительные сведения о агрегатных функциях см. в разделе [предложение Aggregate](../../../language-reference/queries/aggregate-clause.md).  
  
 Принудительно вызвать немедленное выполнение запросов позволяют также методы `ToList` и `ToArray`. Это пригодится в том случае, если требуется выполнить запрос немедленно и кэшировать результаты. Дополнительные сведения об этих методах см. в разделе [Преобразование типов данных](../../concepts/linq/converting-data-types.md).  
  
 Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML в Visual Basic  
 Функции XML в Visual Basic включают XML-литералы и свойства осей XML, которые позволяют легко создавать, получать доступ к XML и изменять их в коде. Литералы XML позволяют записывать XML непосредственно в код. Компилятор Visual Basic обрабатывает XML как объект данных первого класса.  
  
 В приведенном ниже примере кода показано, как создать элемент XML, получить доступ к его дочерним элементам и атрибутам и сделать запросы к содержимому элемента с помощью LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Дополнительные сведения см. в разделе [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Связанные ресурсы  
  
|Раздел|Описание|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Описывает возможности XML в Visual Basic, которые можно запрашивать и которые позволяют включать XML как объекты данных первого класса в код Visual Basic.|  
|[Запросы](../../../language-reference/queries/index.md)|Содержит справочные сведения о предложениях запросов, доступных в Visual Basic.|  
|[Встроенный язык запросов LINQ](../../concepts/linq/index.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to Objects.|  
|[LINQ to ADO.NET (Страница портала)](../../concepts/linq/linq-to-adonet-portal-page.md)|Содержит ссылки на общие сведения, руководства по программированию и примеры для LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Содержит общие сведения, рекомендации по программированию и примеры для LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Практические руководства и пошаговые инструкции
 [How to: Query a Database](how-to-query-a-database-by-using-linq.md) (Практическое руководство. Выполнение запросов к базе данных)  
  
 [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md) (Практическое руководство. Вызов хранимой процедуры)  
  
 [How to: Modify Data in a Database](how-to-modify-data-in-a-database-by-using-linq.md) (Практическое руководство. Изменение данных в базе данных)  
  
 [How to: Combine Data with Joins](how-to-combine-data-with-linq-by-using-joins.md) (Практическое руководство. Объединение данных с помощью соединений)  
  
 [How to: Sort Query Results](how-to-sort-query-results-by-using-linq.md) (Практическое руководство. Сортировка результатов запроса)  
  
 [How to: Filter Query Results](how-to-filter-query-results-by-using-linq.md) (Практическое руководство. Фильтрование результатов запроса)  
  
 [How to: Count, Sum, or Average Data](how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)  
  
 [How to: Find the Minimum or Maximum Value in a Query Result](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)  
  
 [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Рекомендуемые главы книги  
 [Глава 17. LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) в [программировании Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>См. также:

- [Встроенный язык запросов LINQ](../../concepts/linq/index.md)
- [Общие сведения о LINQ to XML в Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Общие сведения о LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
