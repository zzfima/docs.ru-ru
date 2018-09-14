---
title: Написание первого запроса LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 4c04c00c5392d8ba363346b06c806ec79041c439
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45597723"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Написание первого запроса LINQ (Visual Basic)
*Запрос* представляет собой выражение, извлекающее данные из источника данных. Запросы выражаются на языке запросов выделенного. Со временем различных языков были разработаны для различных типов источников данных, например, SQL для реляционных баз данных и XQuery для XML. Поэтому для разработчиков приложений изучать новый язык запросов для каждого типа источника данных или формата данных, который поддерживается.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] упрощает ситуацию, реализуя согласованную модель для работы с данными для различных типов источников и форматов данных. В запросе [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] вы всегда работаете с объектами. Использовать одинаковые базовые шаблоны кода для запроса и преобразования данных в XML-документах, баз данных SQL, наборы данных ADO.NET и сущности, коллекции .NET Framework и любые другие источника или формат, для которого [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] доступен поставщик. В этом документе описываются три фазы создания и использования основных [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов.  
  
## <a name="three-stages-of-a-query-operation"></a>Три этапа операции запроса  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] операции запроса состоят из трех действий:  
  
1.  Получение одного или нескольких источника данных.  
  
2.  создание запроса;  
  
3.  выполнение запроса.  
  
 В [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], выполнение запроса отличается от создания запроса. Все данные не извлекаются только путем создания запроса. Эта особенность обсуждается более подробно далее в этом разделе.  
  
 В следующем примере показано три части операции запроса. В примере используется массив целых чисел в качестве удобного источника данных для демонстрационных целей. Тем не менее те же принципы применимы и к другим источникам данных.  
  
> [!NOTE]
>  На [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), убедитесь, что **Option infer** присваивается **на**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Результат  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Источник данных  
 Так как источник данных в предыдущем примере является массивом, он неявно поддерживает универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс. Это этот факт, что позволяет использовать массив в качестве источника данных для [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса. Типы, которые поддерживают <xref:System.Collections.Generic.IEnumerable%601> или производный интерфейс, например универсальный интерфейс <xref:System.Linq.IQueryable%601>, называются *запрашиваемыми типами*.  
  
 Как неявно запрашиваемым типом, массив не требует изменения или специальной обработки, чтобы служить [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] источника данных. То же самое верно для любого типа коллекции, который поддерживает <xref:System.Collections.Generic.IEnumerable%601>, включая универсальные <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>и другие классы в библиотеке классов .NET Framework.  
  
 Если источник данных не реализует <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] поставщика необходима для реализации функциональности *стандартные операторы запросов* для этого источника данных. Например [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обрабатывает работу по загрузке XML-документ в запрашиваемый <xref:System.Xml.Linq.XElement> тип, как показано в следующем примере. Дополнительные сведения о стандартных операторах запросов см. в разделе [Обзор операторов стандартных запросов (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 С помощью [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], сначала создайте объектно реляционное сопоставление во время разработки вручную либо с помощью [средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) в Visual Studio. Вы создаете запросы к объектам, а [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] во время выполнения обрабатывает взаимодействие с базой данных. В следующем примере `customers` представляет собой определенную таблицу в базе данных и <xref:System.Data.Linq.Table%601> поддерживает универсальный <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Дополнительные сведения о способах создания определенных типов источников данных см. в документации для различных поставщиков [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. (Список этих поставщиков, см. в разделе [LINQ (Language-Integrated Query)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) Общее правило очень просто: [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] источник данных — это любой объект, который поддерживает универсальный <xref:System.Collections.Generic.IEnumerable%601> интерфейс или интерфейс, наследуемый от него.  
  
> [!NOTE]
>  Типы, такие как <xref:System.Collections.ArrayList> , которые поддерживают неуниверсальный <xref:System.Collections.IEnumerable> интерфейс может также использоваться как [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] источников данных. Пример, использующий <xref:System.Collections.ArrayList>, см. в разделе [как: выполнение запроса к ArrayList с помощью LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Запрос  
 В запросе указывается, какие сведения, которые требуется извлечь из источника или источников данных. У вас также есть возможность указать, как эти данные отсортированы, группирования или структурированные перед возвратом. Чтобы включить создание запросов, Visual Basic включен новый синтаксис запроса в язык.  
  
 При выполнении запроса в следующем примере возвращает все четные числа из массива целых `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Выражение запроса содержит три предложения: `From`, `Where`, и `Select`. Определенную функцию и назначение каждого предложения выражения запроса рассматривается в [основные операции запроса (Visual Basic)](basic-query-operations.md). Дополнительные сведения см. в разделе [запросы](../../../../visual-basic/language-reference/queries/index.md). Обратите внимание, что в [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], определение запроса часто хранится в переменной и выполнен позже. Запрос переменной, например `evensQuery` в предыдущем примере, необходимо иметь запрашиваемый тип. Тип `evensQuery` является `IEnumerable(Of Integer)`, назначенный компилятором, использование вывода локального типа.  
  
 Это важно помнить, что сама переменная запроса не выполняет никаких действий и не возвращает никаких данных. Она только хранит определение запроса. В предыдущем примере это `For Each` цикл, который выполняет запрос.  
  
## <a name="query-execution"></a>Выполнение запроса  
 Выполнение запроса отличается от создания запроса. Создание запроса определяет запрос, но выполнение инициируется другого механизма. Возможность выполнения запросов, как только она определена (*немедленное выполнение*), или его определение может быть сохранено, и запрос будет выполнен позже (*отложенное выполнение*).  
  
### <a name="deferred-execution"></a>Отложенное выполнение  
 Типичный [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса напоминает объявление в предыдущем примере, в котором `evensQuery` определен. Он создает запрос, но не выполняет его немедленно. Вместо этого определение запроса хранится в переменной запроса `evensQuery`. Запрос выполняется позже, обычно с помощью `For Each` цикл, который возвращает последовательность значений, либо путем применения стандартного оператора запроса, такие как `Count` или `Max`. Этот процесс называется *отложенного выполнения*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Для последовательности значений, полученных данных доступ с помощью переменной итерации в `For Each` цикла (`number` в предыдущем примере). Поскольку переменная запроса `evensQuery`, содержит определение запроса, а не результаты запроса, запрос можно выполнять так часто, как с помощью переменной запроса более одного раза. Например возможно базу данных в приложении, постоянно обновляемая отдельным приложением. После создания запроса, который получает данные из базы данных, можно использовать `For Each` цикл, чтобы выполнить запрос повторно, извлекая самые последние данные каждый раз.  
  
 В следующем примере показано, как отложенное выполнение работает. После `evensQuery2` определен и выполнен с `For Each` цикла, как показано в предыдущих примерах, некоторые элементы в источнике данных `numbers` изменяются. Затем второй `For Each` цикла `evensQuery2` еще раз. Результаты будут отличаться, второй раз, поскольку `For Each` цикл снова выполняет запрос, используя новые значения в `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Результат  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Немедленное выполнение  
 При отложенном выполнении запросов определение запроса хранится в переменной запроса для последующего выполнения. При немедленном выполнении запрос выполняется во время его определения. Выполнение запускается при применении метода, которому требуется доступ к отдельным элементам результата запроса. Немедленное выполнение часто принудительно с помощью одного из стандартных операторов запросов, которые возвращают одиночное значение. Примерами являются `Count`, `Max`, `Average`, и `First`. Эти стандартные операторы запросов выполните запрос, как только они применяются для вычисления и возвращают единственное значение. Дополнительные сведения о стандартных операторах запросов, которые возвращают одиночное значение, см. в разделе [операции агрегирования](aggregation-operations.md), [операции с элементами](element-operations.md), и [операции, использующие кванторы](quantifier-operations.md).  
  
 Следующий запрос возвращает количество четных чисел в массив целых чисел. Определение запроса не сохраняется, и `numEvens` — это простой `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Того же результата можно добиться с помощью `Aggregate` метод.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 Можно также принудительно вызвать выполнение запроса путем вызова `ToList` или `ToArray` метод запроса (немедленное) или переменной запроса (отложенный), как показано в следующем коде.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 В предыдущих примерах `evensQuery3` — это запрос переменной, но `evensList` является списком и `evensArray` является массивом.  
  
 С помощью `ToList` или `ToArray` для принудительного немедленного выполнения полезно в сценариях, в которых требуется выполнить запрос немедленно и кэшировать результаты в одном объекте коллекции. Дополнительные сведения об этих методах см. в разделе [преобразование типов данных](converting-data-types.md).  
  
 Можно также вызвать запрос для выполнения с помощью `IEnumerable` метода, такого как <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> метод.  
  
## <a name="see-also"></a>См. также

- [Приступая к работе с LINQ в Visual Basic](getting-started-with-linq.md)  
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
- [Общие сведения о стандартных операторах запроса (Visual Basic)](standard-query-operators-overview.md)  
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
