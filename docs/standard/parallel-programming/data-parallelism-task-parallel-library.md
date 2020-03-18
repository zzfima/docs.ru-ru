---
title: Параллелизм данных (библиотека параллельных задач)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, data
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
ms.openlocfilehash: 72696a41cd3b71f47fdcf43e4ece70ebeb7d34d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123164"
---
# <a name="data-parallelism-task-parallel-library"></a>Параллелизм данных (библиотека параллельных задач)
Понятие *Параллелизм данных* относится к сценариям, в которых одна и та же операция выполняется одновременно (то есть параллельно) для элементов в исходной коллекции или массиве. В параллельных операциях с данными исходная коллекция секционируются таким образом, чтобы несколько потоков могли одновременно работать в разных сегментах.  
  
 Библиотека параллельных задач (TPL) поддерживает параллелизм данных с помощью класса <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>. Этот класс предоставляет параллельные реализации на основе методов циклов [for](../../csharp/language-reference/keywords/for.md) и [foreach](../../csharp/language-reference/keywords/foreach-in.md) (`For` и `For Each` в Visual Basic). Вы пишете логику цикла для <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> или <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> в значительной степени так же, как пишете последовательный цикл. Нет необходимости создавать потоки или очередь рабочих элементов. В базовых циклах нет необходимости применять блокировки. Библиотека параллельных задач обрабатывает все низкоуровневые работы. Чтобы получить дополнительные сведения об использовании <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> скачайте документацию по [шаблонам параллельного программирования и общим сведениям о применении параллельных шаблонов с платформой .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222). В следующем примере кода показан простой цикл `foreach` и его параллельный эквивалент.  
  
> [!NOTE]
> В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 При выполнении параллельного цикла библиотека параллельных задач разделяет источник данных, чтобы цикл мог одновременно работать в нескольких частях. В фоне планировщик заданий разделяет задачу исходя из системных ресурсов и рабочей нагрузки. По возможности планировщик перераспределяет работу по нескольким потокам и процессорам, если рабочая нагрузка становится несбалансированной.  
  
> [!NOTE]
> Можно также указать собственный пользовательский разделитель или планировщик. Дополнительные сведения см. в разделах [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) и [Планировщики задач](xref:System.Threading.Tasks.TaskScheduler).  
  
 Оба метода <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> имеют несколько перегрузок, позволяющих остановить или прервать выполнение цикла, отслеживать состояние цикла в других потоках, обслуживать локальное состояние потока, завершить локальные по отношению к потоку объекты, управлять степенью параллелизма и т. д. Вспомогательные типы, обеспечивающие эту функциональную возможность, включают в себя <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions>, <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> и <xref:System.Threading.CancellationTokenSource>.  
  
 Дополнительные сведения см. в статье [Шаблоны для параллельного программирования: описание и применение в .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222).  
  
 Параллелизм данных с декларативным или подобным запросу синтаксисом поддерживается в PLINQ. Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="related-topics"></a>См. также  
  
|Название|Описание:|  
|-----------|-----------------|  
|[Практическое руководство. Написание простого цикла Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)|Описание способа написания цикла <xref:System.Threading.Tasks.Parallel.For%2A> по какому-либо массиву или индексируемой исходной коллекции <xref:System.Collections.Generic.IEnumerable%601>.|  
|[Практическое руководство. Написание простого цикла Parallel.ForEach](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-foreach-loop.md)|Описание способа написания цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A> по какой-либо исходной коллекции <xref:System.Collections.Generic.IEnumerable%601>.|  
|[Практическое руководство. Остановка цикла Parallel.For или выход из этого цикла](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd460721(v=vs.100))|В этом руководстве описывается, как остановить или приостановить параллельный цикл, чтобы все потоки были информированы об этом действии.|  
|[Практическое руководство. Написание цикла Parallel.For и локальными переменными потока](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|В этом руководстве рассматривается написание цикла <xref:System.Threading.Tasks.Parallel.For%2A>, в котором каждый поток поддерживает частную переменную, которая не видна другим потокам, и синхронизация результатов из всех потоков после завершения цикла.|  
|[Практическое руководство. Написание цикла Parallel.ForEach локальными переменными раздела](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md)|В этом руководстве рассматривается написание цикла <xref:System.Threading.Tasks.Parallel.ForEach%2A>, в котором каждый поток поддерживает частную переменную, которая не видна другим потокам, и синхронизация результатов из всех потоков после завершения цикла.|  
|[Практическое руководство. Отмена цикла Parallel.For или Parallel.ForEach](../../../docs/standard/parallel-programming/how-to-cancel-a-parallel-for-or-foreach-loop.md)|В этом руководстве описывается, как отменить параллельный цикл с помощью <xref:System.Threading.CancellationToken?displayProperty=nameWithType>|  
|[Практическое руководство. Повышение скорости выполнения небольших тел циклов](../../../docs/standard/parallel-programming/how-to-speed-up-small-loop-bodies.md)|В этом руководстве описывается один из способов увеличения скорости выполнения, когда тело цикла очень мало.|  
|[Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Общие сведения о библиотеке параллельных задач.|  
|[Параллельное программирование](../../../docs/standard/parallel-programming/index.md)|Введение в параллельное программирование в .NET Framework|  
  
## <a name="see-also"></a>См. также раздел

- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
