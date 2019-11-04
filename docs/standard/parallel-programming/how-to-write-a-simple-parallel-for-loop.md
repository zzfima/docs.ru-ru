---
title: Практическое руководство. Написание простого цикла Parallel.For
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Parallel.For, How to Write
- for loop, parallel construction in .NET
- parallel for loops, how to use
ms.assetid: 9029ba7f-a9d1-4526-8c84-c88716dba5d4
ms.openlocfilehash: 78f07a4f0118c6bce7a043f111988281ddd6add0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139667"
---
# <a name="how-to-write-a-simple-parallelfor-loop"></a>Практическое руководство. Написание простого цикла Parallel.For

Этот раздел содержит два примера, иллюстрирующих использование метода <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>. Первый использует перегрузку метода <xref:System.Threading.Tasks.Parallel.For%28System.Int64%2CSystem.Int64%2CSystem.Action%7BSystem.Int64%7D%29?displayProperty=nameWithType>, а второй — перегрузку <xref:System.Threading.Tasks.Parallel.For%28System.Int32%2CSystem.Int32%2CSystem.Action%7BSystem.Int32%7D%29?displayProperty=nameWithType>, которые являются двумя простейшими перегрузками метода <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>. Эти две перегрузки метода <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> можно использовать, когда не требуется отменять цикл, прерывать итерации цикла или сохранять локальное состояние по отношению к потоку.

> [!NOTE]
> В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

Первый пример вычисляет размер файлов в одном каталоге. Второй — вычисляет произведение двух матриц.

## <a name="directory-size-example"></a>Пример вычисления размера каталога

Данный пример представлен простой служебной программой командной строки, которая вычисляет общий размер файлов в каталоге. Он ожидает получить путь к одному каталогу в качестве аргумента и сообщает количество и общий размер файлов в этом каталоге. После подтверждения существования каталога он использует метод <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> для перечисления файлов в этом каталоге и определения их размеров. После этого размер каждого файла добавляется в переменную `totalSize`. Обратите внимание, что добавление выполняется путем вызова <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>, чтобы оно имело форму атомарной операции. В противном случае несколько задач могут одновременно попытаться обновить переменную `totalSize`.

[!code-csharp[Conceptual.Parallel.For#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.parallel.for/cs/for1.cs#1)]
[!code-vb[Conceptual.Parallel.For#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.parallel.for/vb/for1.vb#1)]

## <a name="matrix-and-stopwatch-example"></a>Пример с матрицами и таймером

Этот пример использует метод <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> для вычисления произведения двух матриц. Он также демонстрирует использование класса <xref:System.Diagnostics.Stopwatch?displayProperty=nameWithType> для сравнения производительности параллельного цикла и непараллельного цикла. Обратите внимание на то, что поскольку данный пример может создавать большое количество выходных данных, он позволяет перенаправлять выходные данные в файл.

[!code-csharp[TPL_Parallel#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleparallelfor.cs#01)]
[!code-vb[TPL_Parallel#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleparallelfor.vb#01)]

При параллелизации любого кода, включая циклы, одна из важнейших целей — достижение максимального уровня использования процессоров без чрезмерной параллелизации до точки, где издержки параллельной обработки нивелируют выигрыш в производительности. В данном конкретном примере параллелизации подвергается только внешний цикл, так как во внутреннем цикле выполняется не очень большой объем работы. Сочетание небольшого объема работы и нежелательного влияния кэша может привести к снижению производительности во вложенных параллельных циклах. Таким образом, параллелизация только внешнего цикла является лучшим способом обеспечить максимальную выгоду от параллелизма в большинстве систем.

## <a name="the-delegate"></a>Делегат

Третий параметр этой перегрузки <xref:System.Threading.Tasks.Parallel.For%2A> — делегат типа `Action<int>` в C# или `Action(Of Integer)` в Visual Basic. Делегат `Action` всегда возвращает значение void независимо от того, сколько параметров типа он имеет. В Visual Basic поведение `Action` определяется `Sub`. Пример использует для создания делегата лямбда-выражение, но этот делегат можно создать и другими способами. См. дополнительные сведения см. в руководстве по [лямбда-выражениям в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="the-iteration-value"></a>Значение итерации

Этот делегат принимает один входной параметр, значение которого является текущей итерацией. Это значение итерации предоставляется средой выполнения, а его начальным значением является индекс первого элемента в сегменте (части) источника, который обрабатывается в текущем потоке.

Если требуется расширенное управление уровнем параллелизма, используйте одну из перегрузок, принимающих входной параметр <xref:System.Threading.Tasks.ParallelOptions?displayProperty=nameWithType>, например: <xref:System.Threading.Tasks.Parallel.For%28System.Int32%2CSystem.Int32%2CSystem.Threading.Tasks.ParallelOptions%2CSystem.Action%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%7D%29?displayProperty=nameWithType>.

## <a name="return-value-and-exception-handling"></a>Обработка возвращаемых значений и исключений

<xref:System.Threading.Tasks.Parallel.For%2A> возвращает объект <xref:System.Threading.Tasks.ParallelLoopResult?displayProperty=nameWithType> после завершения всех потоков. Это возвращаемое значение полезно при остановке или прерывании итерации цикла вручную, поскольку <xref:System.Threading.Tasks.ParallelLoopResult> хранит такие сведения, как последняя завершенная итерация. Если в одном из потоков возникает одно или несколько исключений, выдается <xref:System.AggregateException?displayProperty=nameWithType>.

В коде этого примера возвращаемое значение <xref:System.Threading.Tasks.Parallel.For%2A> не используется.

## <a name="analysis-and-performance"></a>Анализ и производительность

Для просмотра загрузки ЦП на компьютере можно использовать мастер производительности. В качестве эксперимента увеличьте количество столбцов и строк в матрицах. Чем больше матрицы, тем больше разница в производительности между последовательной и параллельной версиями вычисления. При небольшом размере матрицы последовательная версия выполняется быстрее из-за издержек на формирование параллельного цикла.

Синхронные вызовы общих ресурсов, таких как консоль или файловая система, значительно снижают производительность параллельного цикла. При измерении производительности старайтесь избегать в цикле таких вызовов, как <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>.

## <a name="compile-the-code"></a>Компиляция кода

Скопируйте и вставьте этот код в проект Visual Studio.

## <a name="see-also"></a>См. также

- <xref:System.Threading.Tasks.Parallel.For%2A>
- <xref:System.Threading.Tasks.Parallel.ForEach%2A>
- [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
