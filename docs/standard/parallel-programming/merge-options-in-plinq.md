---
title: Параметры слияние в PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
ms.openlocfilehash: f88f2035fb27567e56792cae8289140129e9c557
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129009"
---
# <a name="merge-options-in-plinq"></a>Параметры слияние в PLINQ
Когда запрос выполняется как параллельный, PLINQ разделяет исходную последовательность между несколькими потоками, чтобы они могли параллельно работать с разными частями. Если результаты будут использоваться в одном потоке, например в цикле `foreach` (`For Each` в Visual Basic), то полученные в каждом потоке результаты нужно объединить в одну последовательность. PLINQ может выполнять разные типы слияния в зависимости от операторов, которые присутствуют в запросе. Например, для операторов, изменяющих порядок результатов, необходимо собрать в буфер все элементы из всех потоков. Для потока ожидающего такой результат (и для пользователя приложения) может пройти достаточно большой период времени, пока появятся первые результаты полностью буферизованного запроса. Другие операторы по умолчанию используют частичную буферизацию, то есть возвращают результаты несколькими пакетами. Один оператор (<xref:System.Linq.ParallelEnumerable.ForAll%2A>) по умолчанию не использует буферизацию. Он немедленно выдает все элементы из всех потоков.  
  
 С помощью метода <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>, как показано в следующем примере, можно предоставить PLINQ подсказку с требуемым типом слияния.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Полный пример см. в подразделе [Практическое руководство. Задание параметров слияния в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Если выполняемый запрос не поддерживает запрошенный вариант, этот параметр просто игнорируется. В большинстве случаев нет необходимости указывать параметр слияния для запроса PLINQ. Однако, в некоторых случаях тесты и (или) измерения показывают, что запрос лучше всего выполняется в нестандартном режиме. Чаще всего этот параметр используется, чтобы заставить оператор с частичной буферизацией выдавать все результаты в общем потоке. Это позволяет улучшить скорость реагирования интерфейса на действия пользователя.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 Перечисление <xref:System.Linq.ParallelMergeOptions> включает следующие параметры, которые позволяют выбрать для поддерживаемых форм запросов режим упорядочивания конечных результатов, если эти результаты используются в одном потоке.  
  
- `Not Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions.NotBuffered> требует немедленно возвращать каждый обработанный элемент из каждого потока сразу же после его создания. Это поведение аналогично "потоковой передаче" выходных данных. Если в запросе присутствует оператор <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>, `NotBuffered` сохраняет порядок исходных элементов. Несмотря на то, что в режиме `NotBuffered` немедленно возвращаются все готовые результаты, общее время обработки все равно может оказаться выше, чем для других параметров слияния.  
  
- `Auto Buffered`  
  
     При использовании параметра <xref:System.Linq.ParallelMergeOptions.AutoBuffered> запрос собирает элементы в буфер и затем периодически выдает все содержимое буфера сразу потоку-потребителю. Такое поведение аналогично выдаче исходных данных блоками, в отличие от потоковой передачи в режиме `NotBuffered`. При выборе `AutoBuffered` может потребоваться больше времени, чем при `NotBuffered`, чтобы передать первый элемент в поток-потребитель. Размер буфера и точное поведение выдачи настроить нельзя, и они могут быть разными в зависимости от нескольких характеристик запроса.  
  
- `FullyBuffered`  
  
     Параметр <xref:System.Linq.ParallelMergeOptions.FullyBuffered> требует собирать все выходные данные запроса в единый буфер, и лишь затем возвращать его элементы. В этом режиме потребуется больше всего времени до передачи первого элемента в поток-потребитель, но зато полные результаты могут быть получены быстрее, чем при использованием других вариантов.  
  
## <a name="query-operators-that-support-merge-options"></a>Операторы запроса, поддерживающие параметры слияния  
 В следующей таблице перечислены операторы, которые поддерживают все параметры слияния, а также указаны возможные ограничения.  
  
|Оператор|Ограничения|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Неупорядоченные запросы, использующие в качестве источника только массив или список.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Неупорядоченные запросы, использующие в качестве источника только массив или список.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Нет|  
  
 Все остальные операторы запроса PLINQ могут игнорировать указанные пользователем параметры слияния. Некоторые операторы запроса, например <xref:System.Linq.ParallelEnumerable.Reverse%2A> и <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, не могут вернуть ни одного элемента результата, пока не будут созданы и упорядочены все элементы. Таким образом, если в запросе есть параметр <xref:System.Linq.ParallelMergeOptions> и оператор типа <xref:System.Linq.ParallelEnumerable.Reverse%2A>, этот параметр слияния при обработке не применяется, пока не завершится выдача результатов этого оператора.  
  
 Поддержка некоторых параметров слияния некоторыми операторами зависит от типа исходной последовательности и наличия оператора <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> в более ранней позиции этого запроса. <xref:System.Linq.ParallelEnumerable.ForAll%2A> всегда использует <xref:System.Linq.ParallelMergeOptions.NotBuffered>, то есть возвращает все элементы немедленно. <xref:System.Linq.ParallelEnumerable.OrderBy%2A> всегда использует <xref:System.Linq.ParallelMergeOptions.FullyBuffered>, то есть сортирует полный список перед выдачей любых результатов.  
  
## <a name="see-also"></a>См. также

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
- [Практическое руководство. Задание параметров слияния в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
