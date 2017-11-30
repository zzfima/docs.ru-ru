---
title: "Пользовательские разделители для PLINQ и TPL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12d234b86b0067178d54d2fdcb5d37ceaee6109d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Пользовательские разделители для PLINQ и TPL
Распараллеливании операции над источником данных, одним из основных шагов является *секции* источника на несколько секций, могут получать несколько потоков одновременно. PLINQ и библиотеке параллельных задач (TPL) предоставляют модули разделения по умолчанию, которые работают прозрачно при написании параллельного запроса или <xref:System.Threading.Tasks.Parallel.ForEach%2A> цикла. Для более сложных сценариев можно подключить собственный модуль разделения.  
  
## <a name="kinds-of-partitioning"></a>Типы разделения  
 Существует много способов разделения источника данных. В наиболее эффективный подходах совместно работают несколько потоков процесса исходной последовательности, а не физического разделения источника на несколько подпоследовательностей. Для массивов и других индексированных источников, таких как <xref:System.Collections.IList> коллекций, где длина известен заранее, *диапазонам* является простым типом разделения. Каждый поток получает уникальные индексы начала и конца, поэтому для обработки диапазона источника без перезаписи или перезаписи другим потоком. Только нагрузка, вызванная диапазонам, служат началом процесса создания диапазонов; После этого требуется никакой дополнительной синхронизации. Таким образом он может предоставлять хорошую производительность при условии, что рабочая нагрузка распределяется равномерно. Диапазонам недостаток заключается в том, если один поток завершает рано, он не может помочь завершают свою работу других потоков.  
  
 Для связанных списков и других коллекций, длина которого не известен, можно использовать *разделение по блокам*. В разделение по блокам, каждый поток или задачу в параллельном цикле или запрос использует некоторое количество исходных элементов в одном блоке, обрабатывает их и затем возвращается к извлечению дополнительных элементов. Модуль разделения гарантирует распределение всех элементов и что нет повторяющихся значений. Фрагмент может быть любого размера. Например, модуль разделения, представленный в [как: реализация динамических разделов](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) создает блоки, содержащие только один элемент. При условии, что блоки не слишком велик, этот тип секционирования по своей природе балансировки нагрузки, так как назначение элементов потокам не предопределено. Тем не менее разделитель трудозатрат, синхронизация каждый раз необходимо получить другой фрагмент данных потока. Объем синхронизации в этих случаях обратно пропорционально размеру блоков.  
  
 В общем случае диапазонам выполняется только быстрее, если время выполнения делегата малого до среднего и источник имеет большое количество элементов и трудозатраты каждой секции, примерно равно. Разделение по блокам таким образом обычно происходят быстрее, в большинстве случаев. В источниках с небольшим числом элементов или длительным временем выполнения делегата производительность блоков и диапазонам то примерно равно.  
  
 Модули разделения TPL также поддерживает динамическое количество разделов. Это означает, что можно создать разделы на лету, например, если <xref:System.Threading.Tasks.Parallel.ForEach%2A> цикла вызывает новую задачу. Эта функция позволяет модулю разделения масштабироваться вместе с циклом. Динамические модули разделения также являются по своей природе балансировки нагрузки. При создании пользовательского модуля разделения, необходимо поддерживать динамическое секционирование, чтобы можно было использовать в <xref:System.Threading.Tasks.Parallel.ForEach%2A> цикла.  
  
### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Настройка разделители для PLINQ балансировки нагрузки  
 Некоторые перегрузки <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> позволяют создать разделения для массива или <xref:System.Collections.IList> источника и укажите, является ли он предпринять попытку распределения рабочей нагрузки между потоками. При настройке балансировки нагрузки разделитель используется разделение по блокам и элементы передаются в каждый раздел небольшими фрагментами по запросу. Такой подход гарантирует, что все разделы будут содержать элементы для обработки, пока весь цикл или завершения запроса. Дополнительные перегрузка может использоваться для балансировки нагрузки структурировать любого <xref:System.Collections.IEnumerable> источника.  
  
 Как правило балансировки нагрузки требует, чтобы относительно часто запрашивали элементы из модуля разделения разделы. Напротив модуль разделения, осуществляющий статическое разделение можно назначить элементы каждого модуля разделения за один раз, используя диапазон или разделение по блокам. Это требует меньше ресурсов, чем для распределения нагрузки, но может занять больше времени, если один поток обрабатывает значительно сложнее, чем другие. По умолчанию при передаче IList или массив, PLINQ всегда использует диапазонам без балансировки нагрузки. Чтобы включить балансировку нагрузки для PLINQ, используйте `Partitioner.Create` метод, как показано в следующем примере.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 Лучший способ определения ли использовать нагрузки Балансировка в любом заданном сценарии — проведение экспериментов и измерение длительности выполнения операций при типичных нагрузках и конфигурациях компьютера. Например статическое разделение может обеспечить значительное ускорение на компьютере для многоядерных процессоров с небольшим количеством ядер, но он может привести к замедлению на компьютерах, имеющих относительно большим количеством ядер.  
  
 В следующей таблице перечислены доступные перегрузки <xref:System.Collections.Concurrent.Partitioner.Create%2A> метод. Эти разделители не только для использования только с PLINQ или <xref:System.Threading.Tasks.Task>. Они также могут использоваться с любой пользовательской параллельной конструкции.  
  
|Перегрузка|Использует распределение нагрузки|  
|--------------|-------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Всегда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Если логический аргумент имеет значение true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Если логический аргумент имеет значение true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Никогда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Никогда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Никогда|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Никогда|  
  
### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Настройка разделители статический диапазон для Parallel.ForEach  
 В <xref:System.Threading.Tasks.Parallel.For%2A> цикла, тело цикла предоставляется методу в качестве делегата. Затраты ресурсов при вызове делегата посвящен таким же, как вызов виртуального метода. В некоторых сценариях может быть достаточно мал, затраты на вызов делегата в каждой итерации цикла становится значительные тела параллельного цикла. В такой ситуации, можно использовать один из <xref:System.Collections.Concurrent.Partitioner.Create%2A> перегрузок, чтобы создать <xref:System.Collections.Generic.IEnumerable%601> секций диапазона по элементам источника. Затем можно передать в этой коллекции диапазонов, которые <xref:System.Threading.Tasks.Parallel.ForEach%2A> , тело которого состоит из обычного метода `for` цикла. Преимущество этого подхода является то, что делегат затраты ресурсов на вызов только один раз в диапазоне, а не один раз для каждого элемента. В следующем примере показан базовый шаблон.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Каждый поток цикла получает свой собственный <xref:System.Tuple%602> , содержащий начальное и конечное значения индекса указанного поддиапазона. Внутренний `for` цикл использует `fromInclusive` и `toExclusive` значения для перебора массива или <xref:System.Collections.IList> напрямую.  
  
 Один из <xref:System.Collections.Concurrent.Partitioner.Create%2A> перегрузки позволяет указать размер секций и секций. Эта перегрузка может использоваться в сценариях, где обработку каждого элемента, даже один вызов виртуального метода на один элемент оказывает значительное влияние на производительность низкий.  
  
## <a name="custom-partitioners"></a>Пользовательские разделители  
 В некоторых случаях его может быть оправдан или даже необходимо реализовать собственный модуль разделения. Например может потребоваться настраиваемый класс коллекции, можно разделить более эффективно, чем значение по умолчанию разделители можно на основе сведений из внутренней структуре класса. Или можно создать секции диапазона различных размеров в зависимости от сведений о том, как время, необходимое на обработку элементов, расположенных в разных местах исходной коллекции.  
  
 Чтобы создать базовый пользовательский модуль разделения, наследуйте класс от <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> и переопределить виртуальные методы, как описано в следующей таблице.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Этот метод вызывается основным потоком один раз и возвращает IList(IEnumerator(TSource)). Каждый рабочий поток цикла или запроса можно вызвать `GetEnumerator` в списке, чтобы получить <xref:System.Collections.Generic.IEnumerator%601> из отдельного раздела.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Вернуть `true` при реализации <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, в противном случае `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Если <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> — `true`, этот метод может вызываться при необходимости вместо <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Если результаты должны быть сортируемого или требуется индексный доступ в элементы, являются производными от <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> и переопределять его виртуальные методы, как описано в следующей таблице.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Этот метод вызывается основным потоком один раз и возвращает `IList(IEnumerator(TSource))`. Каждый рабочий поток цикла или запроса можно вызвать `GetEnumerator` в списке, чтобы получить <xref:System.Collections.Generic.IEnumerator%601> из отдельного раздела.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Вернуть `true` при реализации <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>; в противном случае — значение false.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|Как правило, это просто вызывает <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Если <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> — `true`, этот метод может вызываться при необходимости вместо <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 В следующей таблице приведены дополнительные сведения о том, как три вида балансировки нагрузки реализуйте разделители <xref:System.Collections.Concurrent.OrderablePartitioner%601> класса.  
  
|Метод или свойство|IList / массив без балансировки нагрузки|IList / массив с балансировкой нагрузки|IEnumerable|  
|----------------------|-------------------------------------------|----------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Использует диапазонам|Использует разделение по блокам оптимизированное для списков с указанным partitionCount|Использует разделение по блокам посредством создания статического количества секций.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Выдает неподдерживаемое исключение|Использует разделение по блокам для списков и динамических разделов|Использует разделение по блокам посредством создания динамического количества секций.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Возвращает `true`.|Возвращает `true`.|Возвращает `true`.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Возвращает `true`.|Возвращает `false`.|Возвращает `false`.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Возвращает `true`.|Возвращает `true`.|Возвращает `true`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Возвращает `false`.|Возвращает `true`.|Возвращает `true`.|  
  
### <a name="dynamic-partitions"></a>Динамические разделы  
 Если предполагается разделитель для использования в <xref:System.Threading.Tasks.Parallel.ForEach%2A> метод, необходимо будет вернуть динамических несколько секций. Это означает, что разделитель можно задать перечислитель для новой секции по требованию в любое время при выполнении цикла. По сути каждый раз, когда цикл добавляет новую параллельную задачу, он запрашивает новый раздел для этой задачи. Если требуется, чтобы данные должны быть упорядоченными, являются производными от <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> , чтобы каждому элементу в каждой секции, присваивается уникальный индекс.  
  
 Дополнительные сведения и пример см. в разделе [как: реализация динамических разделов](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### <a name="contract-for-partitioners"></a>Контракт для модулей разделения  
 При реализации пользовательского модуля разделения, придерживайтесь следующих правил для обеспечения правильного взаимодействия с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A> в TPL:  
  
-   Если <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> вызывается с аргументом нулю или меньше для `partitionsCount`, исключение <xref:System.ArgumentOutOfRangeException>. Несмотря на то, что PLINQ и TPL никогда не передают `partitionCount` равно 0, тем не менее рекомендуется предотвратить возможность.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>и <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> всегда должны возвращать `partitionsCount` число секций. Если разделитель не хватает данных и не удается создать запрошенный столько секций, метод должен возвращать пустой перечислитель для каждого из остальных разделов. В противном случае вызывает исключение PLINQ и TPL <xref:System.InvalidOperationException>.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, и <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> никогда не должны возвращать `null` (`Nothing` в Visual Basic). Если они есть, PLINQ и библиотеке параллельных задач вызывает исключение <xref:System.InvalidOperationException>.  
  
-   Методы, возвращающие разделы, всегда должны возвращать секции, которые можно полностью и однозначно перечислить источник данных. Должна существовать дублирующихся в источнике данных или пропущенные элементы, если только специально конструктора модуля разделения. Если это правило не соблюдены, может быть нарушен порядок выходных данных.  
  
-   Следующие логические получатели всегда должны точно возвращать следующие значения, чтобы не нарушать порядок выходных данных:  
  
    -   `KeysOrderedInEachPartition`: Каждый раздел возвращает элементы с увеличением ключа индексов.  
  
    -   `KeysOrderedAcrossPartitions`: Для всех секций, которые возвращаются индексы ключа секции *я* выше, чем индексы ключа секции *я*-1.  
  
    -   `KeysNormalized`: Все индексы ключа монотонно без промежутков, начиная с нуля.  
  
-   Все индексы должны быть уникальными. Не может быть повторяющиеся индексы. Если это правило не соблюдены, может быть нарушен порядок выходных данных.  
  
-   Все индексы должны быть неотрицательными. Если это правило не соблюдены, PLINQ и TPL могут вызывать исключения.  
  
## <a name="see-also"></a>См. также  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)  
 [Практическое руководство. Реализация динамических секций](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)  
 [Практическое руководство. Реализация разделителя для статического секционирования](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
