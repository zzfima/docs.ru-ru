---
title: Трансляция стандартных операторов запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: af22b6a895fef8037eb5c069ffb7cb23d1333531
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833684"
---
# <a name="standard-query-operator-translation"></a>Трансляция стандартных операторов запросов

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует стандартные операторы запросов в команды SQL. Обработчик запросов базы данных определяет семантику выполнения преобразования SQL.

Стандартные операторы запросов определяются для *последовательностей*. Последовательность *упорядочена* и зависит от ссылочного удостоверения для каждого элемента последовательности. Дополнительные сведения см. в разделе [Общие сведения о стандартныхC#операторах запросов ()](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) или [Общие сведения о стандартных операторах запросов (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

SQL работает преимущественно с *неупорядоченными наборами значений*. Упорядочение, которое, как правило, задается явным образом, является операцией завершающей обработки, применяемой к окончательному результату запроса, а не к промежуточным результатам. Идентификация определяется значениями. По этой причине SQL-запросы обрабатываются с использованием множества наборов (*сумки*) вместо *наборов*.

Далее приводится описание различий между стандартными операторами запросов и их преобразованиями SQL для поставщика SQL Server для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

## <a name="operator-support"></a>Поддержка операторов

### <a name="concat"></a>Concat

Метод <xref:System.Linq.Enumerable.Concat%2A> определен для упорядоченных множественных наборов, в которых порядок получателя и аргумента совпадают. <xref:System.Linq.Enumerable.Concat%2A> работает как `UNION ALL` для нескольких наборов, за которыми следует общий порядок.

Завершающее действие состоит в упорядочении в SQL перед возвратом результатов. <xref:System.Linq.Enumerable.Concat%2A> не сохраняет порядок своих аргументов. Чтобы обеспечить соответствующее упорядочение, необходимо явно упорядочить результаты метода <xref:System.Linq.Enumerable.Concat%2A>.

### <a name="intersect-except-union"></a>Intersect, Except, Union

Методы <xref:System.Linq.Enumerable.Intersect%2A> и <xref:System.Linq.Enumerable.Except%2A> правильно определяются только для наборов. Семантика для мультинаборов не определена.

Метод <xref:System.Linq.Enumerable.Union%2A> определен для мультинаборов как неупорядоченное объединение мультинаборов (в действительности, он возвращает результат, аналогичный предложению UNION ALL в SQL).

### <a name="take-skip"></a>Take, Skip

методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> хорошо определены только для *упорядоченных наборов*. Семантика для неупорядоченных наборов или мультинаборов не определена.

> [!NOTE]
> <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> имеют определенные ограничения, когда они используются в запросах к SQL Server 2000. Дополнительные сведения см. в записи "пропуск и получение исключений в SQL Server 2000" раздела [Устранение неполадок](troubleshooting.md).

Из-за ограничений по упорядочению в SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] пытается переместить порядок аргументов этих методов в результат метода. Рассмотрим, например, следующий запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

В созданных для этого кода командах SQL упорядочение перемещается в конец:

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

Становится очевидным, что при объединении методов <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> все указанные операции упорядочения должны быть согласованными. В противном случае результаты не определены.

Методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> правильно определяются для неотрицательных постоянных интегральных аргументов, соответствующих спецификации стандартных операторов запросов.

### <a name="operators-with-no-translation"></a>Операторы без преобразования

Перечисленные ниже методы не преобразуются технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Причиной этого, чаще всего, является различие между неупорядоченными мультинаборами и последовательностями.

|Операторы|Обоснование|
|---------------|---------------|
|<xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>|SQL-запросы работают с мультинаборами и не работают с последовательностями. `ORDER BY` должно быть последним предложением, примененным к результатам. По этой причине преобразование общего назначения для этих двух методов отсутствует.|
|<xref:System.Linq.Enumerable.Reverse%2A>|Преобразование этого метода возможно для упорядоченных наборов, однако в настоящее время он не преобразуется технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|
|<xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A>|Преобразование этих методов возможно для упорядоченных наборов, однако в настоящее время они не преобразуются технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|
|<xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|Запросы SQL работают с мультинаборами и не работают с индексируемыми последовательностями.|
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (перегрузка с аргументом по умолчанию)|В общем случае значение по умолчанию для произвольного кортежа указать невозможно. В некоторых случаях для кортежей можно указать нулевые значения через внешние соединения.|

## <a name="expression-translation"></a>Преобразование выражений

### <a name="null-semantics"></a>Семантика значений NULL

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не накладывает семантику сравнения значений NULL в SQL. Операторы сравнения синтаксически преобразуются в эквивалентные команды SQL. По этой причине семантика отражает семантику SQL в соответствии с параметрами сервера или подключения. Например, два значения NULL считаются неравными в параметрах SQL Server по умолчанию, но можно изменить параметры, чтобы изменить семантику. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не учитывает параметры сервера при преобразовании запросов.

Сравнение с литералом NULL преобразуется в соответствующую версию SQL (`is null` или `is not null`).

Значение `null` в параметрах сортировки определяется SQL Server. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не изменяет параметры сортировки.

### <a name="aggregates"></a>Агрегатные выражения

Агрегатный метод <xref:System.Linq.Enumerable.Sum%2A>, который входит в состав стандартных операторов запросов, выполняет сравнение с нулем для поиска пустой последовательности или последовательности, содержащей только значения NULL. В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]семантика SQL остается неизменной, а <xref:System.Linq.Enumerable.Sum%2A> вычисляется до `null` вместо нуля для пустой последовательности или для последовательности, содержащей только значения NULL.

Ограничения SQL для промежуточных результатов применяются к агрегатным выражениям в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Результат метода <xref:System.Linq.Enumerable.Sum%2A>, суммирующего 32-разрядные целые значения, вычисляется не на основе 64-разрядных результатов. При преобразовании [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для метода <xref:System.Linq.Enumerable.Sum%2A> может произойти переполнение даже в том случае, если выполнение реализации стандартного оператора запроса для соответствующей последовательности в памяти не приводит к переполнению.

Аналогичным образом преобразование [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для метода <xref:System.Linq.Enumerable.Average%2A>, вычисляющего среднее значение целых чисел, возвращает тип `integer`, а не `double`.

### <a name="entity-arguments"></a>Аргументы сущностей

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] позволяет использовать типы сущностей в методах <xref:System.Linq.Enumerable.GroupBy%2A> и <xref:System.Linq.Enumerable.OrderBy%2A>. При преобразовании этих операторов использование аргумента типа рассматривается как указание всех членов данного типа. Ниже приведены примеры эквивалентного кода.

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a>Сравниваемые и проверяемые на равенство аргументы

Ниже перечислены методы, в реализации которых требуется равенство аргументов.

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает равенство и сравнение для *неструктурированных* аргументов, но не для аргументов, которые являются или содержат последовательности. Плоский аргумент представляет собой тип, который можно сопоставить со строкой SQL. Проекция одного или нескольких типов сущностей, которые можно статически определить как не содержащие последовательностей, считается плоским аргументом.

Ниже приведены примеры неструктурированных аргументов.

[!code-csharp[DLinqSQOTranslation#3](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

Ниже приведены примеры неструктурированных (иерархических) аргументов.

[!code-csharp[DLinqSQOTranslation#4](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a>Преобразование функций Visual Basic

Ниже перечислены используемые компилятором Visual Basic вспомогательные функции, которые преобразуются в соответствующие операторы и функции SQL.

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

Методы преобразования:

|||||
|-|-|-|-|
|ToBoolean|ToSByte|ToByte|ToChar|
|ToCharArrayRankOne|ToDate|ToDecimal|ToDouble|
|ToInteger|ToUInteger|ToLong|ToULong|
|ToShort|ToUShort|ToSingle|ToString|

## <a name="inheritance-support"></a>Поддержка наследования

### <a name="inheritance-mapping-restrictions"></a>Ограничения сопоставления при наследовании

Дополнительные сведения см. [в разделе Инструкции: Map иерархии наследования](how-to-map-inheritance-hierarchies.md).

### <a name="inheritance-in-queries"></a>Наследование в запросах

В проекции поддерживаются только приведения типов C#. Приведения типов, используемые в других средах, пропускаются и не преобразуются. Помимо преобразования имен функций SQL, SQL фактически выполняет действия, эквивалентные операциям класса <xref:System.Convert> среды CLR. Это означает, что SQL может изменить значение одного типа на значение другого типа. Здесь нет операции, эквивалентной приведению типов в среде CLR, поскольку отсутствует понятие повторной интерпретации тех же битов как битов другого типа. По этой причине приведение типов C# работает только на локальном компьютере. Оно не используется для удаленного взаимодействия.

Операторы `is` и `as`, а также метод `GetType` не ограничены оператором `Select`. Они могут использоваться также и в других операторах запроса.

## <a name="sql-server-2008-support"></a>Поддержка SQL Server 2008

Начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1), LINQ to SQL поддерживает сопоставление с новыми типами даты и времени, которые появились в SQL Server 2008. Однако операторы запросов LINQ to SQL, которые иногда используются при обработке значений, сопоставляемых с этими новыми типами, имеют определенные ограничения.

### <a name="unsupported-query-operators"></a>Неподдерживаемые операторы запросов

Следующие операторы запросов не поддерживаются для значений, сопоставляемых с новыми типами даты и времени SQL Server: `DATETIME2`, `DATE`, `TIME` и `DATETIMEOFFSET`.

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

Дополнительные сведения о сопоставлении с этими SQL Server типами даты и времени см. в разделе [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md).

## <a name="sql-server-2005-support"></a>Поддержка SQL Server 2005

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает следующие функции SQL Server 2005:

- Хранимые процедуры, написанные для среды SQL CLR.

- Пользовательский тип.

- Функции запросов XML.

## <a name="sql-server-2000-support"></a>Поддержка SQL Server 2000

Следующие ограничения SQL Server 2000 (по сравнению с Microsoft SQL Server 2005) влияют на поддержку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

### <a name="cross-apply-and-outer-apply-operators"></a>Операторы «Cross Apply» и «Outer Apply»

Эти операторы недоступны в SQL Server 2000. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] пытается выполнить ряд операций перезаписи, чтобы заменить их соответствующими объединениями.

для навигации по связям создаются `Cross Apply` и `Outer Apply`. Набор запросов, для которого такие операции перезаписи возможны, не является правильно определенным. По этой причине минимальный набор запросов, поддерживаемых для SQL Server 2000, — это набор, не охватывающий навигацию по связям.

### <a name="text--ntext"></a>text / ntext

Типы данных `text` / `ntext` не могут использоваться в определенных операциях запросов к `varchar(max)` / `nvarchar(max)`, которые поддерживаются Microsoft SQL Server 2005.

Способов разрешения проблем, связанных с этим ограничением, не существует. В частности, метод `Distinct()` нельзя использовать для результата, который содержит члены, сопоставленные с `text` или `ntext`.

### <a name="behavior-triggered-by-nested-queries"></a>Поведение, инициируемое вложенными запросами

Связыватель SQL Server 2000 (до SP4) имеет некоторые особенности, активируемые вложенными запросами. Набор запросов SQL, которые инициируют эти особенности, не является правильно определенным. По этой причине нельзя определить набор [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]ных запросов, которые могут вызвать SQL Server исключения.

### <a name="skip-and-take-operators"></a>Операторы «Skip» и «Take»

<xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> имеют определенные ограничения, когда они используются в запросах к SQL Server 2000. Дополнительные сведения см. в записи "пропуск и получение исключений в SQL Server 2000" раздела [Устранение неполадок](troubleshooting.md).

## <a name="object-materialization"></a>Материализация объектов

Материализация создает объекты среды CLR из строк, возвращаемых одним или несколькими запросами SQL.

- Следующие вызовы *выполняются локально* как часть материализации:

  - Конструкторы

  - `ToString` методов в проекциях

  - Приведения типов в проекциях

- Методы, которые следуют за методом <xref:System.Linq.Enumerable.AsEnumerable%2A>, *выполняются локально*. Этот метод не приводит к немедленному выполнению.

- В качестве типа возвращаемых данных результата запроса или члена типа результата можно использовать значение `struct`. Сущности должны быть классами. Анонимные типы материализуются как экземпляры классов, но в проекциях можно использовать структуры (не сущности).

- Член типа возвращаемого значения может быть типом, реализующим интерфейс <xref:System.Linq.IQueryable%601>. Он материализуется как локальная коллекция.

- Следующие методы вызывают *немедленное материализации* последовательности, к которой применяются методы.

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a>См. также:

- [Ссылки](reference.md)
- [Возврат или пропуск элементов последовательности](return-or-skip-elements-in-a-sequence.md)
- [Сцепление двух последовательностей](concatenate-two-sequences.md)
- [Возврат разности наборов между двумя последовательностями](return-the-set-difference-between-two-sequences.md)
- [Возврат пересечения наборов двух последовательностей](return-the-set-intersection-of-two-sequences.md)
- [Возврат объединения наборов двух последовательностей](return-the-set-union-of-two-sequences.md)
