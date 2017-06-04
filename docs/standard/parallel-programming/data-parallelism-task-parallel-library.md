---
title: "Data Parallelism (Task Parallel Library) | Microsoft Docs"
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
  - "parallelism, data"
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
caps.latest.revision: 25
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 25
---
# Data Parallelism (Task Parallel Library)
Понятие *Параллелизм данных* относится к сценариям, в которых одна и та же операция выполняется одновременно \(то есть параллельно\) для элементов в исходной коллекции или массиве.  В параллельных операциях с данными исходная коллекция секционируются таким образом, чтобы несколько потоков могли одновременно работать в разных сегментах.  
  
 Библиотека параллельных задач \(TPL\) поддерживает параллелизм данных с помощью класса <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>.  Этот класс предоставляет параллельные реализации на основе методов циклов [for](../Topic/for%20\(C%23%20Reference\).md) и [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md) \(`For` и `For Each` в Visual Basic\).  Вы пишете логику цикла для <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> или <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> в значительной степени так же, как пишете последовательный цикл.  Нет необходимости создавать потоки или очередь рабочих элементов.  В базовых циклах нет необходимости применять блокировки.  Библиотека параллельных задач обрабатывает все низкоуровневые работы.  Для получения подробных сведений об использовании <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> загрузите документ [Шаблоны параллельного программирования. Общие сведения и применение параллельных шаблонов с платформой .NET Framework 4](http://www.microsoft.com/download/details.aspx?id=19222).  В следующем примере кода показан простой цикл `foreach` и его параллельный эквивалент.  
  
> [!NOTE]
>  В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда\-выражения.  Если вы не знакомы с лямбда\-выражениями в C\# или Visual Basic, см. раздел [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 При выполнении параллельного цикла библиотека параллельных задач разделяет источник данных, чтобы цикл мог одновременно работать в нескольких частях.  В фоне планировщик заданий разделяет задачу исходя из системных ресурсов и рабочей нагрузки.  По возможности планировщик перераспределяет работу по нескольким потокам и процессорам, если рабочая нагрузка становится несбалансированной.  
  
> [!NOTE]
>  Можно также указать собственный пользовательский разделитель или планировщик.  Дополнительные сведения см. в разделах [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) и [Task Schedulers](../Topic/Task%20Schedulers.md).  
  
 Оба метода <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> имеют несколько перегрузок, позволяющих остановить или прервать выполнение цикла, отслеживать состояние цикла в других потоках, обслуживать локальное состояние потока, завершить локальные по отношению к потоку объекты, управлять степенью параллелизма и т. д.  Вспомогательные типы, обеспечивающие эту функциональную возможность, включают в себя <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions>, <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> и <xref:System.Threading.CancellationTokenSource>.  
  
 Дополнительные сведения см. в разделе [Шаблоны параллельного программирования](http://go.microsoft.com/fwlink/p/?LinkId=265491).  
  
 Параллелизм данных с декларативным или подобным запросу синтаксисом поддерживается в PLINQ.  Дополнительные сведения см. в разделе [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## См. также  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)|Описание способа написания цикла <xref:System.Threading.Tasks.Parallel.For%2A> по какому\-либо массиву или индексируемой исходной коллекции <xref:System.Collections.Generic.IEnumerable%601>.|  
|[How to: Write a Simple Parallel.ForEach Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-foreach-loop.md)|Описание способа написания цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A> по какой\-либо исходной коллекции <xref:System.Collections.Generic.IEnumerable%601>.|  
|[How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/ru-ru/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)|В этом руководстве описывается, как остановить или приостановить параллельный цикл, чтобы все потоки были информированы об этом действии.|  
|[How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|В этом руководстве рассматривается написание цикла <xref:System.Threading.Tasks.Parallel.For%2A>, в котором каждый поток поддерживает частную переменную, которая не видна другим потокам, и синхронизация результатов из всех потоков после завершения цикла.|  
|[How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md)|В этом руководстве рассматривается написание цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A>, в котором каждый поток поддерживает частную переменную, которая не видна другим потокам, и синхронизация результатов из всех потоков после завершения цикла.|  
|[How to: Cancel a Parallel.For or ForEach Loop](../../../docs/standard/parallel-programming/how-to-cancel-a-parallel-for-or-foreach-loop.md)|В этом руководстве описывается, как отменить параллельный цикл с помощью <xref:System.Threading.CancellationToken?displayProperty=fullName>|  
|[How to: Speed Up Small Loop Bodies](../../../docs/standard/parallel-programming/how-to-speed-up-small-loop-bodies.md)|В этом руководстве описывается один из способов увеличения скорости выполнения, когда тело цикла очень мало.|  
|[Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Общие сведения о библиотеке параллельных задач.|  
|[Parallel Programming](../../../docs/standard/parallel-programming/index.md)|Введение в параллельное программирование в .NET Framework|  
  
## См. также  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)