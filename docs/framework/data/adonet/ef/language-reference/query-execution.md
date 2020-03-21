---
title: Выполнение запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0e6cf23-63ac-47dd-bfe9-d5bdca826fac
ms.openlocfilehash: e372744eea3eed7fc3f7ee9c8bbdd711c95b586e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149977"
---
# <a name="query-execution"></a>Выполнение запроса
После создания пользователем запрос LINQ преобразуется в дерево команд. Дерево команд является представлением запроса, совместимым с платформой Entity Framework. Затем дерево команд выполняется в источнике данных. Во время выполнения запроса вычисляются все включенные в него выражения (компоненты запроса), в том числе выражения для материализации запроса.  
  
 Выражения выполняются в различные моменты времени. Запросы LINQ всегда выполняются во время прохода по переменной запроса, а не в момент ее создания. Это называется *отложенным исполнением.* Существует возможность принудительно выполнить запрос немедленно - это может оказаться полезным для кэширования результатов запроса. Этот вопрос обсуждается ниже в данном разделе.  
  
 При выполнении запроса в технологии LINQ to Entities некоторые выражения запроса могут выполняться на сервере, а некоторые части — локально, на клиенте. Вычисление выражения на клиенте происходит до выполнения запроса на сервере. Если выражение вычисляется на клиенте, результат этого вычисления подставляется в запрос вместо выражения, после чего запрос выполняется на сервере. Запросы выполняются применительно к источнику данных, поэтому конфигурация источника данных переопределяет правила работы, заданные на клиенте. Например, порядок обработки значений NULL и точность числа зависят от параметров настройки сервера. Все исключения, возникшие на сервере во время выполнения запроса, передаются непосредственно клиенту.  

> [!TIP]
> Для удобного резюме операторов запросов в формате таблицы, которое позволяет быстро определить поведение оператора исполнения, [см. Классификация операторов стандартных запросов по manner of Execution (C )](../../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md).

## <a name="deferred-query-execution"></a>Отложенное выполнение запроса  
 В запросе, возвращающем последовательность значений, переменная запроса никогда не содержит результаты запроса, а только хранит его команды. Выполнение запроса откладывается, пока переменная запроса используется в циклах `foreach` или `For Each`. Это называется *отложенным исполнением;* то есть выполнение запроса происходит через некоторое время после построения запроса. Это означает, что запрос можно выполнять настолько часто, насколько это необходимо. Такое свойство полезно, например, если имеется база данных, которая обновляется другими приложениями. В собственном приложении можно создать запрос, который регулярно выполняется, каждый раз получая последние обновленные данные.  
  
 Отложенное выполнение позволяет объединять несколько запросов или расширять один запрос. При расширении запроса он изменяется, включая в себя новые операции, а последующее выполнение отразит эти изменения. В следующем примере первый запрос возвращает все продукты. Второй запрос расширяет первый, используя предложение `Where`, чтобы возвратить все продукты с размером «L»:  
  
 [!code-csharp[DP L2E Conceptual Examples#Composing1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#composing1)]
 [!code-vb[DP L2E Conceptual Examples#Composing1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#composing1)]  
  
 После выполнения запроса во всех последующих запросах будут использоваться операторы LINQ из памяти. Изменение переменной запроса в цикле с помощью инструкции `foreach` или `For Each` либо путем вызова одного из операторов преобразования LINQ приводит к немедленному выполнению запроса. Эти операторы преобразования включают: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> и <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
## <a name="immediate-query-execution"></a>Немедленное выполнение запроса  
 В отличие от отложенного выполнения запросов, возвращающих последовательность значений, запросы, возвращающие одноэлементное значение, выполняются немедленно. Примерами одноэлементных запросов являются <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.First%2A> и <xref:System.Linq.Enumerable.Max%2A>. Они выполняются немедленно, потому что запрос должен создать последовательность, чтобы вычислить одноэлементный результат. Можно также принудительно вызвать немедленное выполнение. Это может оказаться полезным в тех случаях, когда результаты запроса необходимо поместить в кэш. Чтобы немедленно выполнить запрос, который не возвращает одноэлементное значение, можно вызвать метод <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> или <xref:System.Linq.Enumerable.ToArray%2A> запроса или переменной запроса. В следующем примере метод <xref:System.Linq.Enumerable.ToArray%2A> вызывается для немедленного вычисления последовательности с получением массива.  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
 Можно также принудительно вызвать выполнение, поместив цикл `foreach` или `For Each` сразу после выражения запроса, однако при вызове метода <xref:System.Linq.Enumerable.ToList%2A> или <xref:System.Linq.Enumerable.ToArray%2A> все данные будут помещены в кэш в одном объекте коллекции.  
  
## <a name="store-execution"></a>Выполнение в хранилище  
 Как правило, выражения LINQ to Entities вычисляются на сервере, и не следует ожидать, что поведение выражений будет соответствовать семантике среды CLR; вместо этого применяется семантика источника данных. Однако из этого правила существуют исключения, например, когда выражение выполняется на клиенте. Это может привести к непредвиденным результатам, например, когда сервер и клиент находятся в разных часовых поясах.  
  
 Некоторые выражения запроса могут выполняться на клиенте. Большинство операций по выполнению запроса выполняются на сервере. Помимо методов, выполняемых применительно к элементам запроса, сопоставленным с источником данных, в запросе часто существуют выражения, которые могут быть выполнены локально. Локальное выполнение выражения запроса возвращает значение, которое можно использовать для выполнения запроса или построения результата.  
  
 Некоторые операции всегда выполняются на клиенте, например, привязка значений, вложенные выражения, вложенные запросы из замыканий и материализация объектов в результаты запроса. В итоге получается, что эти элементы (например, значения параметров) не могут обновляться во время выполнения. Анонимные типы могут быть созданы прямо внутри источника данных, однако лучше этого не делать. В источнике данных можно также создавать встроенные группирования, однако не следует это делать в каждом экземпляре. Как правило, лучше не делать никаких предположений относительно объектов, создаваемых на сервере.  
  
 В этом разделе описаны сценарии, в которых код выполняется локально на клиенте. Для получения дополнительной информации о том, какие типы выражений выполняются локально, [см.](expressions-in-linq-to-entities-queries.md)  
  
### <a name="literals-and-parameters"></a>Литералы и параметры  
 Локальные переменные (например, переменная `orderID` в приведенном ниже примере) вычисляются на клиенте.  
  
 [!code-csharp[DP L2E Conceptual Examples#LiteralParameter1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#literalparameter1)]
 [!code-vb[DP L2E Conceptual Examples#LiteralParameter1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#literalparameter1)]  
  
 Параметры методов также вычисляются на клиенте. Например, ниже показан параметр `orderID`, передаваемый методу `MethodParameterExample`.  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodParameterExample](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodparameterexample)]
 [!code-vb[DP L2E Conceptual Examples#MethodParameterExample](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodparameterexample)]  
  
### <a name="casting-literals-on-the-client"></a>Приведение литералов на клиенте  
 Приведение значения `null` к типу CLR выполняется на клиенте.  
  
 [!code-csharp[DP L2E Conceptual Examples#NullCastToString](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#nullcasttostring)]
 [!code-vb[DP L2E Conceptual Examples#NullCastToString](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#nullcasttostring)]  
  
 Приведение к типу, допускающему значение NULL (например, <xref:System.Decimal>), выполняется на клиенте.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastToNullable](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#casttonullable)]
 [!code-vb[DP L2E Conceptual Examples#CastToNullable](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#casttonullable)]  
  
### <a name="constructors-for-literals"></a>Конструкторы для литералов  
 Новые типы CLR, которые могут быть сопоставлены с типами концептуальной модели, выполняются на клиенте.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstructorForLiteral](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constructorforliteral)]
 [!code-vb[DP L2E Conceptual Examples#ConstructorForLiteral](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constructorforliteral)]  
  
 Новые массивы также выполняются на клиенте.  
  
## <a name="store-exceptions"></a>Исключения в хранилище  
 Все ошибки хранилища, обнаруженные во время выполнения запроса, передаются клиенту без сопоставления и обработки.  
  
## <a name="store-configuration"></a>Конфигурация хранилища  
 Когда запрос выполняется в хранилище, конфигурация хранилища переопределяет все правила, заданные на клиенте и для всех операций и выражений применяется семантика хранилища. Это может привести к тому, что выполнение будет производиться по-разному в среде CLR и в хранилище для таких областей, как сравнение со значением NULL, упорядочение идентификаторов GUID, точность операций, в которых участвуют неточные типы данных (например, типы с плавающей запятой или <xref:System.DateTime>), а также строковые операции. Важно помнить об этом при изучении результатов запроса.  
  
 Например, ниже представлены некоторые отличия в работе среды CLR и SQL Server.  
  
- SQL Server упорядочивает идентификаторы GUID иначе, чем среда CLR.  
  
- Кроме того, возможны различия в точности результатов при работе с типом Decimal в SQL Server. Это происходит из-за требований к фиксированной к точности для десятичного типа данных в SQL Server. Например, арифметическое среднее трех значений типа <xref:System.Decimal> - 0,0, 0,0 и 1,0 в памяти на клиенте будет равно 0,3333333333333333333333333333, а в хранилище - 0,333333 (согласно точности по умолчанию для типа Decimal в SQL Server).  
  
- Некоторые операции сравнения строк также обрабатываются в SQL Server иначе, чем в среде CLR. Это связано с тем, что порядок сравнения строк зависит от параметров сортировки на сервере.  
  
- Вызовы функций или методов, включенных в запрос LINQ to Entities, сопоставляются с каноническими функциями платформы Entity Framework, которые затем преобразуются в Transact-SQL и выполняются в базе данных SQL Server. Бывают ситуации, когда сопоставленные функции работают иначе, чем реализации в библиотеках базовых классов. Например, при вызове метода <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A> или <xref:System.String.EndsWith%2A> с пустой строкой в качестве параметра при выполнении в среде CLR возвратит значение `true`, а при выполнении в SQL Server - значение `false`. Кроме того, при вызове метода <xref:System.String.EndsWith%2A> также могут вернуться различные результаты, поскольку SQL Server считает равными две строки, различающиеся только конечными пробелами, в то время как с точки зрения среды CLR эти строки не равны. Это продемонстрировано в следующем примере.  
  
 [!code-csharp[DP L2E Conceptual Examples#CanonicalFuncVsCLRBaseType](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#canonicalfuncvsclrbasetype)]
 [!code-vb[DP L2E Conceptual Examples#CanonicalFuncVsCLRBaseType](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#canonicalfuncvsclrbasetype)]
