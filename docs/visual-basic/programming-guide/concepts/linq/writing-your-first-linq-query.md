---
title: "Написание первого запроса LINQ (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48f1c5e15654580b6e4d060860a0d7001af5e2ef
ms.lasthandoff: 03/13/2017

---
# <a name="writing-your-first-linq-query-visual-basic"></a>Написание первого запроса LINQ (Visual Basic)
Объект *запроса* выражение, которое извлекает данные из источника данных. Запросы выражаются на выделенном языке запросов. Со временем различных языков были разработаны для различных типов источников данных, например SQL для реляционных баз данных и XQuery для XML. Это обуславливает разработчики приложений должны изучать новый язык запросов для каждого типа источника данных или формата данных, который поддерживается.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]упрощает ситуацию, предлагая согласованную модель для работы с данными в различных видах источников и форматов данных. В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запрос, вы всегда работают с объектами. Использовать одинаковые базовые шаблоны кодирования для запроса и преобразования данных в XML-документах, баз данных SQL, наборы данных ADO.NET и сущностей, коллекций .NET Framework и любые другие источника или формата, для которого [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] доступен поставщик. В этом документе описываются три фазы создания и использования основных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов.  
  
## <a name="three-stages-of-a-query-operation"></a>Три этапа операции запроса  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]операции запроса состоят из трех действий:  
  
1.  Получение источника или источников данных.  
  
2.  Создайте запрос.  
  
3.  Выполнение запроса.  
  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], выполнение запроса отличается от создания запроса. Не получить данные, просто создав запрос. Эта точка является более подробно далее в этом разделе.  
  
 В следующем примере показано три части операции запроса. В примере используется массив целых чисел в качестве удобного источника данных для демонстрационных целей. Тем не менее те же принципы применимы и к другим источникам данных.  
  
> [!NOTE]
>  На [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), убедитесь, что **Option infer** равен **на**.  
  
 [!code-vb[VbLINQFirstQuery&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Результат  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Источник данных  
 Так как источник данных в предыдущем примере является массивом, он неявно поддерживает универсальный <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601> Это этот факт, что позволяет использовать массив в качестве источника данных для [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запроса. Типы, которые поддерживают <xref:System.Collections.Generic.IEnumerable%601>или производный интерфейс, например универсальные <xref:System.Linq.IQueryable%601>называются *запрашиваемые типы*.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Являясь неявно запрашиваемым типом, массив не требует изменений или специальной обработки, чтобы служить [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] источника данных. То же справедливо и для любого типа коллекции, который поддерживает <xref:System.Collections.Generic.IEnumerable%601>, включая универсальные <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>и другие классы в библиотеке классов .NET Framework.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Если источник данных еще не реализует <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] поставщика, необходимые для реализации функциональности *стандартные операторы запросов* для этого источника данных.</xref:System.Collections.Generic.IEnumerable%601> Например [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] выполняет работу по загрузке XML-документа в запрашиваемый <xref:System.Xml.Linq.XElement>тип, как показано в следующем примере.</xref:System.Xml.Linq.XElement> Дополнительные сведения о стандартных операторах запросов см. в разделе [Обзор операторов стандартных запросов (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 С [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], сначала создайте объектно реляционного сопоставления во время разработки либо вручную, либо с помощью [средства LINQ to SQL в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) в Visual Studio. Напишите запросы к объектам, а во время выполнения [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] обрабатывает взаимодействие с базой данных. В следующем примере `customers` представляет определенную таблицу в базе данных и <xref:System.Data.Linq.Table%601>поддерживает универсальный <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Data.Linq.Table%601>  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Дополнительные сведения о способах создания определенных типов источников данных см. в документации для различных [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] поставщиков. (Список этих поставщиков см. в разделе [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) Базовое правило заключается в простой: [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] источником данных является любой объект, который поддерживает универсальный <xref:System.Collections.Generic.IEnumerable%601>интерфейс, или интерфейс, наследуемый от его.</xref:System.Collections.Generic.IEnumerable%601>  
  
> [!NOTE]
>  Типы, такие как <xref:System.Collections.ArrayList>, поддерживающие неуниверсальный <xref:System.Collections.IEnumerable>интерфейс может также использоваться как [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] источников данных.</xref:System.Collections.IEnumerable> </xref:System.Collections.ArrayList> Пример, использующий <xref:System.Collections.ArrayList>, в разделе [как: запроса к ArrayList с помощью LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).</xref:System.Collections.ArrayList>  
  
## <a name="the-query"></a>Запрос  
 В запросе указывается, какие сведения, которые требуется извлечь из источника или источников данных. Также имеется возможность указать, как эти данные отсортированы, группирования или структурированные перед возвратом. Для создания запросов, Visual Basic включен новый синтаксис запроса в язык.  
  
 При выполнении запроса в следующем примере возвращает все четные числа из массива целых чисел `numbers`.  
  
 [!code-vb[VbLINQFirstQuery&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Выражение запроса содержит три предложения: `From`, `Where`, и `Select`. Конкретная функциональность и назначение каждого предложения выражения запроса рассматривается в [основные операции запроса (Visual Basic)](basic-query-operations.md). Дополнительные сведения см. в разделе [запросов](../../../../visual-basic/language-reference/queries/queries.md). Обратите внимание, что в [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], определение запроса часто хранится в переменной и выполняется позднее. Запрос переменной, например `evensQuery` в предыдущем примере, должна иметь запрашиваемый тип. Тип `evensQuery` — `IEnumerable(Of Integer)`, назначенный компилятором с помощью вывода локального типа.  
  
 Важно помнить, что сама переменная запроса не выполняет никаких действий и не возвращает никаких данных. Она только хранит определение запроса. В предыдущем примере это `For Each` цикл, который выполняет запрос.  
  
## <a name="query-execution"></a>Выполнение запроса  
 Выполнение запроса отличается от создания запроса. Создание запроса определяет запрос, но выполнение инициируется другим механизмом. Запрос может выполняться сразу после того, как она определена (*немедленное выполнение*), или определение может быть сохранено и запрос может быть выполнен позднее (*отложенного выполнения*).  
  
### <a name="deferred-execution"></a>Отложенное выполнение  
 Типичный [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] напоминает запрос в предыдущем примере, в котором `evensQuery` определен. Запрос создается, но выполняется не сразу. Вместо этого определение запроса хранится в переменной запроса `evensQuery`. Запрос выполняется позже, обычно с помощью `For Each` цикл, который возвращает последовательность значений, или путем применения стандартного оператора запроса, таких как `Count` или `Max`. Этот процесс называется *отложенного выполнения*.  
  
 [!code-vb[VbLINQFirstQuery&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Для последовательности значений, полученных данных доступа с помощью переменной итерации в `For Each` цикла (`number` в предыдущем примере). Поскольку переменная запроса `evensQuery`, содержит определение запроса, а не результаты запроса, запрос можно выполнять так часто, как с помощью переменной запроса более одного раза. Например может потребоваться базы данных в приложении, которое постоянно обновляемая отдельным приложением. После создания запроса, который получает данные из базы данных, можно использовать `For Each` цикл, чтобы выполнить запрос повторно, извлекая каждый раз последние данные.  
  
 В следующем примере показано влияние отложенного выполнения работы. После `evensQuery2` определен и выполнен с `For Each` цикл, как показано в предыдущих примерах, некоторые элементы в источнике данных `numbers` изменяются. Затем второй `For Each` цикла `evensQuery2` еще раз. Результаты отличаются, второй раз, поскольку `For Each` цикл снова выполняет запрос, используя новые значения в `numbers`.  
  
 [!code-vb[VbLINQFirstQuery&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Результат  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Немедленное выполнение  
 При отложенном выполнении запросов определение запроса хранится в переменной запроса для последующего выполнения. При немедленном выполнении запрос выполняется во время его определения. Выполнение инициируется при применении метода, которому требуется доступ к отдельным элементам результата запроса. Немедленное выполнение часто производится принудительно с помощью одного из стандартных операторов запросов, возвращающих одиночное значение. Examples are `Count`, `Max`, `Average`, and `First`. Эти стандартные операторы запросов выполните запрос, как только они применяются для вычисления и возвращают единственное значение. Дополнительные сведения о стандартных операторах запросов, возвращающих отдельные значения в разделе [операции статистической обработки](aggregation-operations.md), [операции с элементами](element-operations.md), и [операции, использующие кванторы](quantifier-operations.md).  
  
 Следующий запрос возвращает количество четных чисел в массив целых чисел. Определение запроса не сохраняется, и `numEvens` – это просто `Integer`.  
  
 [!code-vb[VbLINQFirstQuery&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Того же результата можно добиться с помощью `Aggregate` метод.  
  
 [!code-vb[VbLINQFirstQuery&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 Можно также принудительно выполнить запрос путем вызова `ToList` или `ToArray` метод в запросе (немедленный) или переменной запроса (отложенный), как показано в следующем коде.  
  
 [!code-vb[VbLINQFirstQuery №&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 В предыдущих примерах `evensQuery3` — запрос переменной, но `evensList` приведен список и `evensArray` является массивом.  
  
 С помощью `ToList` или `ToArray` для принудительного немедленного выполнения полезно в сценариях, в которых требуется выполнить запрос немедленно и кэшировать результаты в одном объекте коллекции. Дополнительные сведения об этих методах см. в разделе [преобразование типов данных](converting-data-types.md).  
  
 Можно также заставить запрос для выполнения с помощью `IEnumerable` метода, такого как <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>метод.</xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в Visual Basic](getting-started-with-linq.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Общие сведения о стандартных операторах (Visual Basic)](standard-query-operators-overview.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)
