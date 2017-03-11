---
title: "Написание первого запроса LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [LINQ в Visual Basic], написание"
  - "запросы LINQ [Visual Basic]"
  - "LINQ [Visual Basic], написание запросов"
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 54
---
# Написание первого запроса LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Запрос* представляет собой выражение, извлекающее данные из источника данных.  Запросы выражаются на выделенном языке запросов.  Со временем были разработаны различные языки для различных типов источников данных, например SQL для реляционных баз данных и XQuery для XML.  Поэтому разработчики приложений должны изучать новый язык запросов для каждого поддерживаемого типа источника данных или формата данных.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] упрощает ситуацию, предлагая согласованную модель для работы с данными в различных видах источников и форматов данных.  В запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] работа всегда осуществляется с объектами.  Для запросов и преобразования данных в XML\-документах, базах данных SQL, наборах данных и сущностях ADO.NET, коллекциях .NET Framework и любых других источников или форматов, для которых доступен поставщик [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], используются одинаковые базовые шаблоны кодирования.  В этом документе описываются три фазы создания и использования основных запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  
  
 ![ссылка на видео](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Для просмотра связанных демонстрационных видеороликов перейдите по ссылке [Инструкции. Введение в LINQ](http://go.microsoft.com/fwlink/?LinkId=133021).  
  
## Три этапа операции запроса  
 Операции запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] состоят из трех действий.  
  
1.  Получение источника или источников данных.  
  
2.  Создание запроса.  
  
3.  Выполнение запроса.  
  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] выполнение запроса отличается от создания запроса.  Простое создание запроса не связано с возвращением данных.  Эта особенность обсуждается более подробно далее в этом разделе.  
  
 В следующем примере показаны три части операции запроса.  В примере используется массив целых чисел в качестве удобного источника данных для демонстрационных целей.  Однако те же принципы применимы и к другим источникам данных.  
  
> [!NOTE]
>  На [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), убедитесь, что **Option infer** имеет значение **На**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_1.vb)]  
  
 Результат  
  
 `0 2 4 6`  
  
## Источник данных  
 В предыдущем примере источником данных является массив, поэтому он неявно поддерживает универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>.  Именно этот факт позволяет использовать массив в качестве источника данных для запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Типы, которые поддерживают <xref:System.Collections.Generic.IEnumerable%601> или производный интерфейс как универсальный шаблон <xref:System.Linq.IQueryable%601> вызываются *запрашиваемыми типами*.  
  
 Являясь неявно запрашиваемым типом, массив не требует изменений или специальной обработки, чтобы служить источником данных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  То же самое верно для любого типа коллекции, поддерживает <xref:System.Collections.Generic.IEnumerable%601>, включая универсальные <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> и других классов в библиотеке классов .NET Framework.  
  
 Если источник данных еще не реализует <xref:System.Collections.Generic.IEnumerable%601>, необходим поставщик [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] для реализации функциональности *стандартных операторов запросов* для источника данных.  Например, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] выполняет работу по загрузке XML\-документа в запрашиваемый тип <xref:System.Xml.Linq.XElement>, как показано в следующем примере.  Дополнительные сведения о стандартных операторах запроса см в разделе [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_2.vb)]  
  
 Используя [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], сначала создайте объектно\-реляционное сопоставление в режиме разработки вручную либо с помощью [Реляционный конструктор объектов](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2).  Напишите запросы к объектам, а во время выполнения [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] будет осуществлять взаимодействие с базой данных.  В следующем примере `customers` представляет определенную таблицу в базе данных, а <xref:System.Data.Linq.Table%601> поддерживает универсальный <xref:System.Linq.IQueryable%601>.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Для получения дополнительных сведений о способах создания определенных типов источников данных см. документацию по различным поставщикам [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  \(Список этих поставщиков содержится в разделе [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).\) Основное правило является простым: источник данных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] — это любой объект, поддерживающий универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601> или интерфейс, наследуемый от него.  
  
> [!NOTE]
>  Такие типы, как <xref:System.Collections.ArrayList>, поддерживающие неуниверсальный интерфейс <xref:System.Collections.IEnumerable>, также могут использоваться в качестве источников данных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Пример, использующий <xref:System.Collections.ArrayList> см. в разделе [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md).  
  
## Запрос  
 В запросе указывается, какие сведения требуется извлечь из источника или источников данных.  Также можно указать способ сортировки, группировки или структурирования сведений до их возвращения.  Для создания запросов в язык Visual Basic включен новый синтаксис запроса.  
  
 В следующем примере запрос возвращает все четные числа из массива целых чисел `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_1.vb)]  
  
 Выражение запроса содержит три предложения: `From`, `Where` и `Select`.  Конкретная функциональность и назначение каждого предложения выражения запроса рассматривается в разделе [Основные операции запроса \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  Дополнительные сведения см. в разделе [Запросы](../../../../visual-basic/language-reference/queries/queries.md).  Обратите внимание, что в [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] определение запроса часто хранится в переменной и выполняется позднее.  Переменная запроса, например `evensQuery` в предыдущем примере, должна быть запрашиваемым типом. Тип `evensQuery``IEnumerable(Of Integer)`, присвоенного компилятором, используя вывод локального типа.  
  
 Важно помнить, что сама переменная запроса не выполняет действий и не возвращает никаких данных.  Она только хранит определение запроса.  В предыдущем примере запрос выполняется циклом `For Each`.  
  
## Выполнение запроса  
 Выполнение запроса не зависит от его создания.  Создание запроса определяет запрос, но выполнение инициируется другим механизмом.  Запрос может выполняться по мере его определения \(*немедленное выполнение*\), или его определение может быть сохранено и запрос может быть выполнен позднее \(*отложенное выполнение*\).  
  
### Отложенное выполнение  
 Обычный запрос [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] напоминает запрос в предыдущем примере, в котором определен `evensQuery`.  Запрос создается, но выполняется не сразу.  Определение запроса хранится в переменной запроса `evensQuery`.  Запрос выполняется позже, обычно с помощью цикла `For Each`, который возвращает последовательность значений, или при помощи стандартного оператора запроса, такого как `Count` или `Max`.  Такой процесс называется *отложенным выполнением*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_3.vb)]  
  
 Доступ к извлеченной последовательности значений осуществляется с помощью переменной итерации в цикле `For Each` \(`number` в предыдущем примере\).  Поскольку переменная запроса `evensQuery` содержит определение, а не результаты запроса, запрос можно выполнять так часто, как требуется.  Например, приложение может работать с базой данных, которая непрерывно обновляется отдельным приложением.  После создания запроса, извлекающего данные из базы данных, можно использовать цикл `For Each`, чтобы выполнить запрос повторно, извлекая каждый раз последние данные.  
  
 В следующем примере демонстрируется отложенное выполнение.  После того, как `evensQuery2` определен и выполнен с помощью цикла `For Each`, как в предыдущих примерах, некоторые элементы в источнике данных `numbers` изменяются.  Затем второй цикл `For Each` еще раз выполняет `evensQuery2`.  Результаты, извлеченные во второй раз, отличаются от изначальных, поскольку цикл `For Each` снова выполняет запрос, используя новые значения в `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_4.vb)]  
  
 Результат  
  
 `Evens in original array:`  
  
 `0 2 4 6`  
  
 `Evens in changed array:`  
  
 `0 10 2 22 8`  
  
### Немедленное выполнение  
 При отложенном выполнении запросов определение запроса хранится в переменной запроса для последующего выполнения.  При немедленном выполнении запрос выполняется во время своего определения.  Выполнение инициируется при применении метода, которому необходим доступ к отдельным элементам результата запроса.  Немедленное выполнение часто производится принудительно с помощью одного из стандартных операторов запроса, возвращающего одно значение.  Примерами являются `Count`, `Max`, `Average` и `First`.  Эти стандартные операторы запроса выполняют запрос при осуществлении вычислений и возвращают единственное значение.  Дополнительные сведения о стандартных операторах запроса, возвращающих одно значение, содержатся в разделах [Aggregation Operations](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md), [Element Operations](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md) и [Quantifier Operations](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).  
  
 Следующий запрос возвращает количество четных чисел в массиве целых чисел.  Определение запроса не сохраняется, а `numEvens` является простым `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_5.vb)]  
  
 Того же результата можно добиться с помощью метода `Aggregate`.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_6.vb)]  
  
 Можно также принудительно выполнить запрос путем вызова метода `ToList` или `ToArray` в запросе \(немедленный\) или переменной запроса \(отложенный\), как показано в следующем коде.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/writing-your-first-linq-_7.vb)]  
  
 В предыдущих примерах `evensQuery3` является переменной запроса, `evensList` является списком, а `evensArray` является массивом.  
  
 Использование `ToList` или `ToArray` для принудительного немедленного выполнения полезно в тех сценариях, в которых требуется выполнить запрос немедленно и кэшировать результаты в одном объекте коллекции.  Дополнительные сведения об этих методах см. в разделе [Converting Data Types](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Выполнение запроса можно вызвать с помощью метода `IEnumerable`, например <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>.  
  
## Связанные демонстрационные видеоролики  
 [How Do I: Get Started with LINQ?](http://go.microsoft.com/fwlink/?LinkId=133021)  
  
 [Video How to: Writing Queries in Visual Basic](http://go.microsoft.com/fwlink/?LinkID=100356)  
  
## См. также  
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Примеры LINQ](../Topic/LINQ%20Samples.md)   
 [Общие сведения о реляционном конструкторе объектов](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)