---
title: Написание первого запроса LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 5c83d888f65ce5c216327e94c5d4d1267fb93c29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952000"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Написание первого запроса LINQ (Visual Basic)
*Запрос* представляет собой выражение, извлекающее данные из источника данных. Запросы выражаются на языке выделенных запросов. Со временем разрабатываются разные языки для различных типов источников данных, например SQL для реляционных баз данных и XQuery для XML. Это позволяет разработчику приложения изучать новый язык запросов для каждого поддерживаемого типа источника данных или формата данных.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]упрощает ситуацию, предлагая согласованную модель для работы с данными в различных видах источников данных и форматов. В запросе [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] вы всегда работаете с объектами. Те же самые базовые шаблоны кодирования используются для запроса и преобразования данных в XML-документах, базах данных SQL, ADO.NETх наборов данных и сущностях, .NET Framework коллекциях, а также в любом [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] другом источнике или формате, для которого доступен поставщик. В этом документе описаны три фазы создания и использования основных [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов.  
  
## <a name="three-stages-of-a-query-operation"></a>Три этапа операции запроса  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]операции запроса состоят из трех действий:  
  
1. Получение источника данных или источников.  
  
2. создание запроса;  
  
3. выполнение запроса.  
  
 В [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]службах выполнение запроса отличается от создания запроса. Данные не извлекаются просто путем создания запроса. Эта особенность обсуждается более подробно далее в этом разделе.  
  
 В следующем примере показаны три части операции запроса. В примере в качестве удобного источника данных для демонстрационных целей используется массив целых чисел. Тем не менее те же принципы применимы и к другим источникам данных.  
  
> [!NOTE]
> На [странице Компиляция в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)убедитесь, что **параметр Infer** имеет значение **On**.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Результат  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Источник данных  
 Поскольку источник данных в предыдущем примере является массивом, он неявно поддерживает универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс. Это тот факт, что позволяет использовать массив в качестве источника данных для [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса. Типы, которые поддерживают <xref:System.Collections.Generic.IEnumerable%601> или производный интерфейс, например универсальный интерфейс <xref:System.Linq.IQueryable%601>, называются *запрашиваемыми типами*.  
  
 В качестве неявного запрашиваемого типа массив не требует изменения или специальной обработки, чтобы служить [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] источником данных. Это справедливо и для любого типа коллекции, который поддерживает <xref:System.Collections.Generic.IEnumerable%601>, включая универсальный <xref:System.Collections.Generic.List%601>класс, <xref:System.Collections.Generic.Dictionary%602>и другие классы в библиотеке классов .NET Framework.  
  
 Если исходные данные еще не реализованы <xref:System.Collections.Generic.IEnumerable%601> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] , то для реализации функциональности *стандартных операторов запросов* для этого источника данных требуется поставщик. Например, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обрабатывает работу по загрузке XML-документа в <xref:System.Xml.Linq.XElement> запрашиваемый тип, как показано в следующем примере. Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запросов (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#2)]  
  
 С [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]помощью вы сначала создаете объектно-реляционное сопоставление во время разработки либо вручную, либо с помощью [средств LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) в Visual Studio. Вы создаете запросы к объектам, а [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] во время выполнения обрабатывает взаимодействие с базой данных. В следующем примере `customers` представляет определенную таблицу в базе данных и <xref:System.Data.Linq.Table%601> поддерживает универсальный <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Дополнительные сведения о способах создания определенных типов источников данных см. в документации для различных поставщиков [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. (Список этих поставщиков см. в разделе [LINQ (интегрированный в язык запрос)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) Простое правило: [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] источник данных — это любой объект, который поддерживает универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс, или интерфейс, наследующий от него.  
  
> [!NOTE]
> Такие типы, <xref:System.Collections.ArrayList> как поддержка неуниверсального <xref:System.Collections.IEnumerable> интерфейса, также могут использоваться в качестве [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] источников данных. Пример, в котором используется <xref:System.Collections.ArrayList>, см. в разделе как [ Запрос ArrayList с помощью LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Запрос  
 В запросе указывается, какие сведения необходимо получить из источника или из источников данных. Кроме того, можно указать способ сортировки, группировки или структурирования данных перед их возвратом. Чтобы включить создание запросов, Visual Basic включил в язык новый синтаксис запросов.  
  
 При выполнении запроса, приведенного в следующем примере, возвращаются все четные числа из массива `numbers`целых чисел.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Выражение запроса содержит три предложения: `From`, `Where`и `Select`. Конкретная функция и назначение каждого предложения выражения запроса рассматриваются в разделе [основные операции запроса (Visual Basic)](basic-query-operations.md). Дополнительные сведения см. в разделе [запросы](../../../../visual-basic/language-reference/queries/index.md). Обратите внимание [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], что в, определение запроса часто хранится в переменной и выполняется позже. Переменная запроса, например `evensQuery` , в предыдущем примере, должна быть запрашиваемым типом. Тип `evensQuery` —`IEnumerable(Of Integer)`, назначенный компилятором с помощью определения локального типа.  
  
 Важно помнить, что сама переменная запроса не выполняет никаких действий и не возвращает никаких данных. Он сохраняет только определение запроса. В предыдущем примере `For Each` это цикл, выполняющий запрос.  
  
## <a name="query-execution"></a>Выполнение запроса  
 Выполнение запроса отделено от создания запроса. Создание запроса определяет запрос, но выполнение активируется другим механизмом. Запрос может быть выполнен, как только он определен (немедленное*выполнение*), либо можно сохранить определение, и запрос можно будет выполнить позже (*Отложенное выполнение*).  
  
### <a name="deferred-execution"></a>Отложенное выполнение  
 Типичный [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запрос похож на тот, который приведен в предыдущем примере, в `evensQuery` котором определен. Он создает запрос, но не выполняет его немедленно. Вместо этого определение запроса хранится в переменной `evensQuery`запроса. Запрос выполняется позже, как правило, с помощью `For Each` цикла, который возвращает последовательность значений или применение стандартного оператора запроса, такого как `Count` или `Max`. Этот процесс называется *отложенным выполнением*.  
  
 [!code-vb[VbLINQFirstQuery#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#7)]  
  
 Для последовательности значений можно получить доступ к полученным данным с помощью переменной итерации в `For Each` цикле (`number` в предыдущем примере). Так как переменная `evensQuery`запроса, содержит определение запроса, а не результаты запроса, можно выполнить запрос так часто, как требуется, используя переменную запроса более одного раза. Например, в приложении может быть база данных, которая постоянно обновляется отдельным приложением. После создания запроса, получающего данные из этой базы данных, можно использовать `For Each` цикл для многократного выполнения запроса, получая последние данные каждый раз.  
  
 В следующем примере показано, как работает отложенное выполнение. После `evensQuery2` определения и выполнения `For Each` с помощью цикла, как в предыдущих примерах, некоторые элементы в источнике `numbers` данных изменяются. Затем снова запускается `For Each` `evensQuery2` второй цикл. Результаты отличаются второй раз, так как `For Each` цикл выполняет запрос еще раз, используя новые значения в. `numbers`  
  
 [!code-vb[VbLINQFirstQuery#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#3)]  
  
 Результат  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Немедленное выполнение  
 При отложенном выполнении запросов определение запроса сохраняется в переменной запроса для последующего выполнения. При немедленном выполнении запрос выполняется во время его определения. Выполнение активируется при применении метода, который требует доступа к отдельным элементам результата запроса. Немедленное выполнение часто принудительно осуществляется с помощью одного из стандартных операторов запросов, возвращающих одиночные значения. Примеры: `Count` `Max` ,,и`First`. `Average` Эти стандартные операторы запросов выполняют запрос сразу после применения, чтобы вычислить и вернуть одноэлементный результат. Дополнительные сведения о стандартных операторах запросов, возвращающих одиночные значения, см. в разделе [операции агрегирования](aggregation-operations.md), [операции с элементами](element-operations.md)и [Операции квантификаторов](quantifier-operations.md).  
  
 Следующий запрос возвращает число четных чисел в массиве целых чисел. Определение запроса не сохраняется и `numEvens` является простым. `Integer`  
  
 [!code-vb[VbLINQFirstQuery#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#4)]  
  
 Тот же результат можно получить с помощью `Aggregate` метода.  
  
 [!code-vb[VbLINQFirstQuery#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#5)]  
  
 Можно также принудительно выполнить запрос, вызвав `ToList` метод или `ToArray` для запроса (immediate) или переменной запроса (отложенной), как показано в следующем коде.  
  
 [!code-vb[VbLINQFirstQuery#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#6)]  
  
 В предыдущих примерах `evensQuery3` является переменной запроса, но `evensList` является списком и `evensArray` является массивом.  
  
 Использование `ToList` или`ToArray` для принудительного немедленного выполнения особенно полезно в сценариях, в которых необходимо немедленно выполнить запрос и кэшировать результаты в одном объекте коллекции. Дополнительные сведения об этих методах см. в разделе [Преобразование типов данных](converting-data-types.md).  
  
 Можно также вызвать выполнение запроса с помощью `IEnumerable` метода, такого <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> как метод.  
  
## <a name="see-also"></a>См. также

- [Приступая к работе с LINQ в Visual Basic](getting-started-with-linq.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](standard-query-operators-overview.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
