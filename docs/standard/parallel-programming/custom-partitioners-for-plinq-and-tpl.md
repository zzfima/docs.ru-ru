---
title: "Custom Partitioners for PLINQ and TPL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, partitioners"
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Custom Partitioners for PLINQ and TPL
Одним из основных шагов при распараллеливании операции в источнике данных является *разделение* источника на несколько секций, параллельный доступ к которым имеют сразу несколько потоков.  PLINQ и Библиотека параллельных задач \(TPL\) по умолчанию предоставляют модули разделения, которые работают прозрачно при написании параллельного запроса или цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A>.  Для более сложных сценариев можно подключить собственный модуль разделения.  
  
## Типы разделения  
 Существует много способов разделения источника данных.  В более рациональных решениях над выполнением исходной последовательности совместно работают несколько потоков, вместо физического разделения источника на несколько подпоследовательностей.  Для массивов и других индексированных источников, например, коллекции <xref:System.Collections.IList>, где длина заранее известна, *разделение по диапазонам* является самым простым типом разделения.  Каждый поток получает уникальные индексы начала и конца для обработки диапазона источника без перезаписи источника, а также без перезаписи потока другим потоком.  Только служебные данные, вовлеченные в разделение по диапазонам, служат началом процесса создания диапазонов; после этого никакая дополнительная синхронизация не требуется.  Таким образом, хорошая производительность может быть обеспечена только в том случае, когда рабочая нагрузка распределена равномерно.  Недостаток разделения по диапазонам состоит в том, что поток, завершивший обработку, не может помочь другим потокам.  
  
 Для связанных списков и других коллекций с неизвестной длиной можно использовать *разделение по блокам*.  При разделении по блокам каждый поток или задача в параллельном цикле или запросе в каждом блоке использует некоторое количество исходных элементов, обрабатывает их, а затем возвращается к извлечению дополнительных элементов.  Модуль разделения гарантирует распределение всех элементов и отсутствие их дублирования.  Блок может иметь любой размер.  Например, модуль разделения, показанный в разделе [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md), создает блоки, содержащие только один элемент.  Пока блоки небольшие, этот тип разделения по сути позволяет рационально распределить нагрузку, так как назначение элементов потокам не предопределено.  Однако модуль разделения выполняет синхронизацию служебных данных каждый раз, при переходе потока к другому блоку.  Объем синхронизации, выполняемой в данном случае, обратно пропорционален размеру блоков.  
  
 В общем, разделение по диапазонам выполняется быстрее в случае, когда период времени выполнения делегата находится в диапазоне от короткого до умеренного, источник содержит большое количество элементов, а общее количество усилий, затрачиваемых на обработку каждой секции, приблизительно одинаково.  Таким образом, разделение по блокам в большинстве случаев ускоряет работу.  В источниках с небольшим количеством элементов или длительным временем выполнения делегата производительность разделения по блокам и разделения по диапазонам приблизительно одинакова.  
  
 Модули разделения TPL также поддерживают динамичное количество разделов.  Это означает, что они могут создавать разделы в реальном времени, например, когда цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A> вызывает новую задачу.  Эта функция позволяет модулю разделения масштабироваться вместе с циклом.  Динамические модули разделения также служат для распределения нагрузки.  При создании пользовательского модуля разделения, необходимо поддерживать динамическое разделение из цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A>.  
  
### Настройка модулей распределения нагрузки для PLINQ  
 Несколько перегрузок метода <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName> позволяют создать модуль разделения для массива или источника <xref:System.Collections.IList>, а также указать должен ли он предпринять попытку распределения рабочей нагрузки между потоками.  Если модуль разделения настроен на распределение нагрузки, используется разделение по блокам, и элементы передаются в каждый раздел по запросу маленькими блоками.  Такой подход гарантирует, что все разделы будут содержать элементы для обработки до тех пор, пока весь цикл или запрос не будет выполнен.  Чтобы обеспечить разделение для распределения нагрузки для любого источника <xref:System.Collections.IEnumerable> можно воспользоваться дополнительной перегрузкой.  
  
 Распределение нагрузки требует, чтобы разделы относительно часто запрашивали элементы из модуля разделения.  Напротив, модуль разделения, осуществляющий статическое разделение, может назначить каждому модулю разделения сразу все элементы, используя диапазон или разделение по блокам.  Для этого необходимо меньшее количество перегрузок, чем для распределения нагрузки, но может потребоваться больше времени для обработки, если один поток обрабатывает значительно большее количество задач, чем другие.  По умолчанию, если передается IList или массив, PLINQ всегда использует разделение по диапазонам без распределения нагрузки.  Для применения распределения нагрузки к PLINQ воспользуйтесь методом `Partitioner.Create`, как показано в следующем примере.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 Лучшим способом для определения необходимости использования распределения нагрузки в любом исходном сценарии является проверка и измерение длительности выполнения операций при обычной загрузке и конфигурации компьютера.  Например, статическое разделение может обеспечить значительное ускорение на многоядерном компьютере с небольшим количеством ядер, но на компьютере с относительно большим количеством ядер такое разделение может привести к замедлению обработки.  
  
 В следующей таблице перечислены доступные перегрузки метода <xref:System.Collections.Concurrent.Partitioner.Create%2A>.  Эти модули распределения можно использовать не только для PLINQ или <xref:System.Threading.Tasks.Task>.  Ими также можно воспользоваться в любой пользовательской параллельной конструкции.  
  
|Перегрузка|Использует распределение нагрузки|  
|----------------|---------------------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Всегда|  
|[Create\<TSource\>\(TSource\<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Если логический аргумент имеет значение true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Если логический аргумент имеет значение true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Никогда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Никогда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Никогда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Никогда|  
  
### Настройка статических модулей разделения по диапазону для Parallel.ForEach  
 В цикле <xref:System.Threading.Tasks.Parallel.For%2A>, тело цикла предоставляется методу в качестве делегата.  Затраты ресурсов при вызове делегата приблизительно такие же, как и при вызове виртуального метода.  В некоторых сценариях тело параллельного цикла может быть на столько маленьким, что затраты ресурсов на вызов делегата в каждой итерации цикла становятся значительными.  В такой ситуации можно воспользоваться одной из перегрузок <xref:System.Collections.Concurrent.Partitioner.Create%2A> для создания <xref:System.Collections.Generic.IEnumerable%601> разделов по диапазонам из исходных элементов.  Затем, коллекцию диапазонов можно передать методу <xref:System.Threading.Tasks.Parallel.ForEach%2A>, тело которого состоит из регулярного цикла `for`.  Преимущество такого подхода состоит в том, что затраты ресурсов на вызов делегата происходят только один раз для каждого диапазона, а не один раз для каждого элемента.  В следующем примере демонстрируется использование основного шаблона.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Каждый поток цикла получает собственный <xref:System.Tuple%602>, содержащий значения индексов начала и конца указанного поддиапазона.  Внутренний цикл `for` использует значения `fromInclusive` и `toExclusive` для применения цикла к массиву или непосредственно к <xref:System.Collections.IList>.  
  
 Одна из перегрузок <xref:System.Collections.Concurrent.Partitioner.Create%2A> позволяет указать размер разделов и их количество.  Такая перегрузка может использоваться в сценариях, в которых затраты ресурсов на обработку каждого элемента на столько незначительны, что даже один вызов виртуального метода на каждый элемент оказывает значительное влияние на производительность.  
  
## Пользовательские модули разделения  
 В некоторых сценариях следует или даже необходимо реализовать собственный модуль разделения.  Например, пользовательский класс коллекции, на основании знания его внутренней структуры, можно разделить более эффективно, чем с помощью модулей разделения, установленных по умолчанию.  Либо, при необходимости создания разделов по диапазонам разного размера, зная время, необходимое на обработку элементов, расположенных в разных местах исходной коллекции.  
  
 Чтобы создать базовый пользовательский модуль разделения, наследуйте класс от <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=fullName> и переопределите виртуальные методы, как описано в следующей таблице.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Этот метод вызывается основным потоком один раз и возвращает IList\(IEnumerator\(TSource\)\).  Каждый рабочий поток цикла или запроса может вызвать `GetEnumerator` из списка для извлечения <xref:System.Collections.Generic.IEnumerator%601> из отдельного раздела.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращает `true` при реализации <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, в противном случае `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Если значение <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> равно `true`, то этот метод может быть вызван вместо <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Если результаты должны быть сортируемыми или требуется индексный доступ к элементам, то наследуйте из <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName> и переопределите его виртуальные методы, как описано в следующей таблице.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Этот метод вызывается основным потоком один раз и возвращает `IList(IEnumerator(TSource))`.  Каждый рабочий поток цикла или запроса может вызвать `GetEnumerator` из списка для извлечения <xref:System.Collections.Generic.IEnumerator%601> из отдельного раздела.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращает `true` при реализации <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>, в противном случае false.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|Обычно, это вызывает только <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Если значение <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> равно `true`, то этот метод может быть вызван вместо <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 В следующей таблице приведены дополнительные сведения о реализации класса <xref:System.Collections.Concurrent.OrderablePartitioner%601> с помощью трех типов модулей разделения для распределения нагрузки.  
  
|Метод\/свойство|IList\/массив без распределения нагрузки|IList\/массив с распределением нагрузки|IEnumerable|  
|---------------------|----------------------------------------------|---------------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Использует разделение по диапазонам|Использует разделение по блокам, оптимизированное для списков с указанным partitionCount|Использует разделение по блокам посредством создания статического количества разделов.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=fullName>|Выдает неподдерживаемое исключение|Использует разделение по блокам для списков и динамических разделов|Использует разделение по блокам посредством создания динамического количества разделов.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Возвращает `true`|Возвращает `true`|Возвращает `true`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Возвращает `true`|Возвращает `false`|Возвращает `false`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Возвращает `true`|Возвращает `true`|Возвращает `true`|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращает `false`|Возвращает `true`|Возвращает `true`|  
  
### Динамические разделы  
 Если модуль разделения планируется использовать в методе <xref:System.Threading.Tasks.Parallel.ForEach%2A>, должна быть возможность вернуть динамическое количество разделов.  Это обозначает, что модуль разделения может в любое время в течение цикла по требованию предоставлять перечислитель для нового раздела.  По существу, когда бы цикл не добавлял новую параллельную задачу, он для такой задачи запрашивает новый раздел.  Если данные должны быть упорядоченными, наследуйте из <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName>, так чтобы каждому элементу в каждом разделе присваивался уникальный индекс.  
  
 Дополнительные сведения и примеры см. в разделе [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### Контракт для модулей разделения  
 При реализации пользовательского модуля разделения следуйте следующим инструкциям для обеспечения правильного взаимодействия с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> в TPL:  
  
-   Если <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> вызывается со значением аргумента равным или меньше нуля для `partitionsCount`, вызовите <xref:System.ArgumentOutOfRangeException>.  Хотя PLINQ и TPL никогда не передают `partitionCount` со значением 0, тем не менее, рекомендуем защититься от такой возможности.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> и <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> всегда должны возвращать `partitionsCount` число разделов.  Если модули разделения выполняются не зависимо от данных и не могут создавать требуемое количество разделов, то для каждого из оставшихся разделов метод должен возвращать пустой перечислитель.  В противном случае, как PLINQ, так и TPL выдадут исключение <xref:System.InvalidOperationException>.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> и <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> никогда не должны возвращать `null` \(`Nothing`  в Visual Basic\).  В противном случае, PLINQ \/ TPL выдаст исключение <xref:System.InvalidOperationException>.  
  
-   Методы, возвращающие разделы, всегда должны возвращать разделы, которые могут полностью и однозначно перечислить источник данных.  В источнике данных не допускается дублирование ли пропущенные элементы, кроме особо необходимых для конструктора модуля разделения.  При несоблюдении этого правила, может быть нарушен порядок выхода.  
  
-   Следующие логические получатели всегда должны точно возвращать перечисленные ниже значения, чтобы не нарушать порядок выхода:  
  
    -   `KeysOrderedInEachPartition`. Каждый раздел возвращает элементы с возрастающими ключевыми индексами.  
  
    -   `KeysOrderedAcrossPartitions`. Для всех возвращенных разделов ключевые индексы в разделе *i* выше, чем ключевые индексы в разделе *i*\-1.  
  
    -   `KeysNormalized`. Все ключевые индексы монотонно возрастают без перерывов, начиная с нуля.  
  
-   Все индексы должны быть уникальными.  Не допускается дублирование индексов.  При несоблюдении этого правила, может быть нарушен порядок выхода.  
  
-   Все индексы должны быть неотрицательными.  При несоблюдении этого правила, PLINQ\/TPL может выдать исключение.  
  
## См. также  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)