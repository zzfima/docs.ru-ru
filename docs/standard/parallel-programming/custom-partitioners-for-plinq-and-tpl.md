---
title: Пользовательские разделители для PLINQ и TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
ms.openlocfilehash: 8caea6d8a97b8c0daf7c59718479ea2e12a52d78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141568"
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Пользовательские разделители для PLINQ и TPL

Одним из основных шагов при распараллеливании операции над источником данных является *секционирование* источника, чтобы несколько потоков могли параллельно обращаться к нескольким секциям. PLINQ и библиотека параллельных задач (TPL) предоставляют стандартные средства секционирования, которые прозрачно работают при создании параллельного запроса или цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A>. Для более сложных сценариев вы можете подключить собственное средство секционирования.

## <a name="kinds-of-partitioning"></a>Виды секционирования

Есть много разных способов секционировать источник данных. Самые эффективные подходы позволяют нескольким потокам совместно обрабатывать исходную последовательность, не разделяя источник физически на несколько подпоследовательностей. Для массивов и других индексированных источников, например коллекций <xref:System.Collections.IList>, длина которых известна заранее, проще всего применить *секционирование по диапазонам*. В этом варианте каждый поток получает уникальные индексы начала и окончания диапазона, что позволяет ему обработать свою часть данных без конфликтов с другими потоками. Секционирование по диапазонам привносит только один тип накладных расходов, связанный с начальным процессом создания этих диапазонов. При дальнейшей работе никакой дополнительной синхронизации не требуется. Такой подход обеспечит хорошую производительность, если рабочую нагрузку удастся распределить равномерно. Недостаток секционирования по диапазонам заключается в том, что поток, завершивший работу раньше других, не может помочь другим потокам завершить работу.

Для связанных списков и других коллекций, длина которых неизвестна, можно применить *блочное секционирование*. В этом варианте каждый поток, каждая задача в параллельных циклах или каждый запрос поочередно извлекает определенное количество исходных элементов в виде блока, обрабатывает их и снова обращается за дополнительным блоком элементов. Средство секционирования следит за тем, чтобы все элементы были обработаны строго один раз. Могут использоваться блоки любого размера. Например, средство секционирования из статьи [Практическое руководство. Реализация динамических секций](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) создает блоки размером в один элемент. Если размер блока не слишком велик, такой тип секционирования автоматически правильно балансирует нагрузку, так как не использует предварительное распределение элементов по потокам. Но средство секционирования все же добавляет определенные накладные расходы, связанные с синхронизацией, при каждом получении очередного блока для потока. Степень синхронизации в этом алгоритме обратно пропорциональна размеру блоков.

В целом секционирование по диапазонам выполняется быстрее только в том случае, если делегат выполняется за малый или средний период времени, а источник имеет большое количество элементов и трудозатраты на каждую секцию примерно одинаковы. Соответственно, блочное секционирование в большинстве случаев работает быстрее. Для источников с небольшим числом элементов или для делегатов с продолжительным временем выполнения производительность этих двух типов секционирования примерно равна.

Средства секционирования библиотеки TPL также поддерживают динамическое количество секций. Такой подход означает создание секций "на лету", например при создании новой задачи в цикле <xref:System.Threading.Tasks.Parallel.ForEach%2A>. Эта функция позволяет средству секционирования масштабироваться синхронно с циклом. Динамические средства секционирования также автоматически балансируют нагрузку. Если вы создаете собственное средство секционирования, обязательно обеспечьте поддержку динамического секционирования из цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A>.

### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Настройка средств секционирования с балансировкой нагрузки для PLINQ

Некоторые перегрузки метода <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> позволяют создать средство секционирования для массива или источника <xref:System.Collections.IList> и выбрать, будет ли он распределять рабочую нагрузку между потоками. Если средство секционирования поддерживает балансировку нагрузки, используется блочное секционирование и элементы распределяются небольшими блоками по мере запрашивания. Такой подход нужен для того, чтобы все секции содержали элементы для обработки до полного завершения цикла или запроса. Можно использовать дополнительные перегрузки, чтобы реализовать балансировку нагрузки для любого источника <xref:System.Collections.IEnumerable>.

Обычно для балансировки нагрузки важно, чтобы секции относительно часто запрашивали новые элементы у средства секционирования. Напротив, средство статического секционирования может распределить все элементы единовременно, используя секционирование по диапазонам или блочное секционирование. Накладные расходы в этом случае будут ниже, чем при балансировке нагрузки, но выполнение может занять больше времени, если одному из потоков достанется существенно больше работы, чем остальным. По умолчанию PLINQ всегда использует секционирование по диапазонам без балансировки нагрузки, когда получает на вход ILIst или массив. Чтобы включить в PLINQ балансировку нагрузки, используйте метод `Partitioner.Create`, как показано в следующем примере.

[!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
[!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]

Самый надежный способ определиться с применением балансировки нагрузки для конкретного сценария — выполнить эксперименты и замерить длительность выполнения операций при типичных нагрузках и разных конфигурациях компьютера. Например статическое секционирование может значительно ускорить работу на компьютере с небольшим количеством ядер, но привести к замедлению работы на компьютерах с относительно большим количеством ядер.

В следующей таблице перечислены все доступные перегрузки метода <xref:System.Collections.Concurrent.Partitioner.Create%2A>. Эти средства секционирования можно использовать не только с PLINQ или <xref:System.Threading.Tasks.Task>. Они пригодны для любой пользовательской конструкции с параллельной обработкой.

|Перегрузка|Использование балансировки нагрузки|
|--------------|-------------------------|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Всегда|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Если передан логический аргумент со значением true|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Если передан логический аргумент со значением true|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Никогда|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Никогда|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Никогда|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Никогда|

### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Настройка средств статического секционирования по диапазонам для Parallel.ForEach

Когда используется цикл <xref:System.Threading.Tasks.Parallel.For%2A>, тело этого цикла передается методу в качестве делегата. Затраты на вызов этого делегата будут примерно такими же, как на вызов виртуального метода. В некоторых сценариях тело цикла параллельной обработки будет настолько небольшим, что затраты на вызов делегата при каждой итерации цикла составят значительную часть нагрузки. В такой ситуации вы можете применить одну из перегрузок <xref:System.Collections.Concurrent.Partitioner.Create%2A>, чтобы создать <xref:System.Collections.Generic.IEnumerable%601> для секций диапазонов, распределив по ним исходные элементы. Эта коллекция диапазонов затем передается в метод <xref:System.Threading.Tasks.Parallel.ForEach%2A>, тело которого состоит из стандартного цикла `for`. Преимущество этого подхода заключается в том, что затраты на вызов делегата применяются только один раз для каждого диапазона, а не для каждого элемента. В следующем примере показан базовый шаблон.

[!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
[!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]

Каждый поток в цикле получает собственный класс <xref:System.Tuple%602>, который содержит начальное и конечное значения индекса для назначенного ему поддиапазона. Внутренний цикл `for` использует значения `fromInclusive` и `toExclusive`, напрямую перебирая массив или <xref:System.Collections.IList>.

Одна из перегрузок <xref:System.Collections.Concurrent.Partitioner.Create%2A> позволяет указать размер и количество секций. Эта перегрузка удобна для тех ситуаций, в которых обработка каждого элемента требует так мало работы, что даже один вызов виртуального метода для каждого элемента существенно снизит производительность.

## <a name="custom-partitioners"></a>Пользовательские разделители

В некоторых случаях будет оправданно или даже необходимо реализовать пользовательское средство секционирования. Например, если у вас есть пользовательский класс коллекции и знание его внутренней структуры позволяет вам секционировать его более эффективно, чем это делают стандартные средства секционирования. Или же вы знаете, что на обработку элементов, расположенных в разных местах исходной коллекции, потребуется разное и прогнозируемое время, а значит можете создать секции с диапазонами разных размеров.

Чтобы создать простое пользовательское средство секционирования, наследуйте класс от <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> и переопределите для него виртуальные методы, которые описаны в следующей таблице.

|||
|-|-|
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Этот метод вызывается основным потоком один раз и возвращает IList(IEnumerator(TSource)). Каждый рабочий поток в цикле или запросе может вызвать `GetEnumerator` для списка, чтобы получить <xref:System.Collections.Generic.IEnumerator%601> по конкретной секции.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращайте `true`, если вы реализовали <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, в противном случае — `false`.|
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Если <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> имеет значение `true`, можно (но не обязательно) вызвать этот метод вместо <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|

Если результаты требуют сортировки или вам нужен доступ к элементам по индексам, наследуйте класс от <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> и переопределите его виртуальные методы, как описано в следующей таблице.

|||
|-|-|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Этот метод вызывается основным потоком один раз и возвращает `IList(IEnumerator(TSource))`. Каждый рабочий поток в цикле или запросе может вызвать `GetEnumerator` для списка, чтобы получить <xref:System.Collections.Generic.IEnumerator%601> по конкретной секции.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращайте `true`, если вы реализовали <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>, или FALSE в противном случае.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|Как правило, он просто вызывает <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Если <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> имеет значение `true`, можно (но не обязательно) вызвать этот метод вместо <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|

В следующей таблице приведены дополнительные сведения о том, как реализован класс <xref:System.Collections.Concurrent.OrderablePartitioner%601> в трех типах средств секционирования с балансировкой нагрузки.

|Метод или свойство|IList или массив без балансировки нагрузки|IList или массив с балансировкой нагрузки|IEnumerable|
|----------------------|-------------------------------------------|----------------------------------------|-----------------|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Использует секционирование по диапазонам|Использует блочное секционирование, оптимизированное для списков с указанным значением partitionCount|Использует блочное секционирование, создавая статическое количество секций.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Создает неподдерживаемое исключение|Использует блочное секционирование для списков и динамических секций|Использует блочное секционирование, создавая динамическое количество секций.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Возвращает `true`.|Возвращает `true`.|Возвращает `true`.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Возвращает `true`.|Возвращает `false`.|Возвращает `false`.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Возвращает `true`.|Возвращает `true`.|Возвращает `true`.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращает `false`.|Возвращает `true`.|Возвращает `true`.|

### <a name="dynamic-partitions"></a>Динамические секции

Если ваше средство секционирования будет использоваться в методе <xref:System.Threading.Tasks.Parallel.ForEach%2A>, нужно поддерживать создание динамического количества секций. Это означает, что средство секционирования в любой момент обработки цикла может передать перечислитель для создания новой секции по требованию. Обычно цикл запрашивает новую секцию для каждой новой параллельной задачи, которую он создает. Если вам важно поддерживать упорядочение данных, наследуйте класс от <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>, чтобы присваивать уникальный индекс каждому элементу в каждой секции.

Дополнительные сведения и пример см. в разделе [Практическое руководство. Реализация динамических секций](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).

### <a name="contract-for-partitioners"></a>Контракт для средств секционирования

Если вы реализуете пользовательское средство секционирования, придерживайтесь следующих рекомендаций для корректного взаимодействия с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> в TPL:

- Если <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> вызывается с аргументом `partitionsCount`, значение которого равно нулю или меньше, создавайте исключение <xref:System.ArgumentOutOfRangeException>. Несмотря на то, что PLINQ и TPL никогда не передают для `partitionCount` значение 0, мы рекомендуем подстраховаться от такой ситуации.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> и <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> должны всегда возвращать число секций (`partitionsCount`). Если у средства секционирования недостаточно данных, чтобы создать требуемое число секций, метод должен возвращать пустой перечислитель для всех остальных секций. В противном случае PLINQ и TPL создадут исключение <xref:System.InvalidOperationException>.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> и <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> никогда не должны возвращать `null` (`Nothing` в Visual Basic). В противном случае PLINQ и (или) TPL создадут исключение <xref:System.InvalidOperationException>.

- Методы, которые возвращают секции, должны всегда возвращать секции, которые способны полностью и однозначно перечислить данные из источника. Не допускайте дублирования или пропуска элементов в источнике данных, если такое поведение не требуется от средства секционирования для конкретных целей. Если вы не будете соблюдать это правило, может быть нарушен порядок выходных данных.

- Следующие методы получения логических значений должны всегда точно возвращать следующие значения, чтобы не нарушать порядок выходных данных:

  - `KeysOrderedInEachPartition`. Каждая секция возвращает элементы в порядке увеличения индексов ключа.

  - `KeysOrderedAcrossPartitions`. Для всех возвращаемых секций соблюдается условие, что все индексы ключа в секции *i* выше, чем все индексы ключа в секции *i*-1.

  - `KeysNormalized`. Все индексы ключа возрастают монотонно и без промежутков, начиная с нуля.

- Все индексы должны быть уникальными. Не допускается повторение индексов. Если вы не будете соблюдать это правило, может быть нарушен порядок выходных данных.

- Все индексы должны быть неотрицательными. Если это правило не соблюдается, PLINQ и (или) TPL могут создавать исключения.

## <a name="see-also"></a>См. также

- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
- [Практическое руководство. Реализация динамических секций](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)
- [Практическое руководство. Реализация разделителя для статического секционирования](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
