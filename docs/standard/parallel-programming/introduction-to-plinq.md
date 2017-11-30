---
title: "Введение в PLINQ"
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
helpviewer_keywords: PLINQ queries, introduction to
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db9c3e16d4a8073fbce636f37490f719dbd93e4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-plinq"></a>Введение в PLINQ
## <a name="what-is-a-parallel-query"></a>Что такое параллельный запрос?  
 Встроенный язык запросов (LINQ) был впервые представлен в [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].  Он поддерживает унифицированную модель для выполнения запросов к любой <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> источника данных в строго типизированным образом. LINQ-объекты — это имя для запросов LINQ, выполняемые к коллекции в памяти, такие как <xref:System.Collections.Generic.List%601> и массивы. В этой статье предполагается, что у вас уже есть общие представления о LINQ. Дополнительные сведения см. в разделе [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).  
  
 Parallel LINQ (PLINQ) является параллельной реализацией шаблона LINQ. Запрос PLINQ во многом напоминает непараллельный запрос LINQ to Objects. Запросы PLINQ, так же как последовательные [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] запросы, работают с любой в памяти <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> данных источника и имеют возможность отложенного выполнения, поэтому они не начинают выполняться, пока запрос перечислен. Основное различие состоит в том, что PLINQ пытается задействовать сразу все процессоры в системе. Для этого он разбивает источник данных на сегменты, а затем запрашивается каждый сегмент в отдельном рабочем потоке сразу, используя сразу несколько процессоров. Во многих случаях параллельное выполнение значительно сокращает время выполнения запроса.  
  
 Благодаря параллельному выполнению PLINQ можно добиться значительное повышение производительности сравнению с устаревшим кодом для определенных типов запросов часто просто путем добавления <xref:System.Linq.ParallelEnumerable.AsParallel%2A> операции с источником данных запроса. Тем не менее параллелизм может представлять свои собственные сложности, и не все операции запросов в PLINQ выполняются быстрее. Некоторые запросы при применении параллелизма только замедляются. В связи с этим необходимо понимать, как влияют на параллельные запросы такие аспекты, как упорядочение. Дополнительные сведения см. в разделе [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
> [!NOTE]
>  В этой документации для определения делегатов в PLINQ используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 Далее в этой статье приводится обзор основных классов PLINQ и обсуждаются способы создания запросов PLINQ. Каждый раздел содержит ссылки на более подробные сведения и примеры кода.  
  
## <a name="the-parallelenumerable-class"></a>Класс ParallelEnumerable  
 <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> Класс предоставляет почти все функциональные возможности PLINQ.  Он и остальная часть <xref:System.Linq?displayProperty=nameWithType> пространство имен типов компилируются в сборку System.Core.dll. Проекты C# и Visual Basic по умолчанию в Visual Studio ссылаются на сборку и импортируют пространство имен.  
  
 <xref:System.Linq.ParallelEnumerable>включает реализации всех стандартных операторов запроса, поддерживаемых LINQ to Objects, несмотря на то, что он не будет пытаться параллелизации каждого из них. Если вы не знакомы с [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)], обратитесь к разделу [Введение в LINQ](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e).  
  
 Помимо стандартных операторов запроса <xref:System.Linq.ParallelEnumerable> класс содержит набор методов, которые позволяют использовать поведения, характерные для параллельного выполнения. Методы, характерные для PLINQ, перечислены в следующей таблице.  
  
|Класс ParallelEnumerable|Описание|  
|---------------------------------|-----------------|  
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|Точка входа для PLINQ. Указывает, что по возможности остальная часть запроса должна быть параллелизована.|  
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|Указывает, что остальная часть запроса должна выполняться последовательно, как непараллельный запрос LINQ.|  
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|Указывает, что PLINQ должен сохранить порядок исходной последовательности до конца запроса либо до тех пор, пока порядок не изменится, что может произойти, например, при использовании предложения orderby (Order By в Visual Basic).|  
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|Указывает, что PLINQ для остальной части запроса не обязан сохранять порядок исходной последовательности.|  
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|Указывает, что PLINQ должен периодически отслеживать состояние предоставленного токена отмены и отменить выполнение, если он будет запрошен.|  
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|Указывает максимальное количество процессоров, которое PLINQ должен использовать для параллелизации запроса.|  
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|Предоставляет подсказку о том, каким образом PLINQ должен объединять параллельные результаты в одну последовательность в потоке-потребителе, если это возможно.|  
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|Указывает, должен ли PLINQ параллелизовать запрос, даже если по умолчанию он должен выполняться последовательно.|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Многопоточный метод перечисления в отличие от итерации результатов запроса может обрабатываться параллельно без предварительного объединения с потоком-потребителем.|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>перегрузка|Перегрузка, которая является уникальной для PLINQ и обеспечивает промежуточное агрегирование локальных разделов потока, а также функцию окончательного агрегирования, позволяющую объединять результаты всех разделов.|  
  
## <a name="the-opt-in-model"></a>Модель с явным согласием  
 При написании запроса согласие на использование PLINQ путем вызова <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> метод расширения в источнике данных, как показано в следующем примере.  
  
 [!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
 [!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]  
  
 <xref:System.Linq.ParallelEnumerable.AsParallel%2A> Метод расширения привязывает последующие операторы запросов, в этом случае `where` и `select`в <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> реализации.  
  
## <a name="execution-modes"></a>Режимы выполнения  
 По умолчанию PLINQ является консервативным. Во время выполнения инфраструктура PLINQ анализирует общую структуру запроса. Если параллелизация может ускорить выполнение запроса, PLINQ разбивает исходную последовательность на задачи, которые выполняются одновременно. Если параллелизовать запрос небезопасно, PLINQ просто выполняет его последовательно. Если PLINQ может выбирать между потенциально затратным параллельным алгоритмом или нетребовательным последовательным алгоритмом, по умолчанию он выбирает алгоритм последовательной обработки. Можно использовать <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> метод и <xref:System.Linq.ParallelExecutionMode?displayProperty=nameWithType> перечисления, чтобы указать PLINQ выбрать алгоритм параллельной обработки. Это пригодится в том случае, если тестирование и измерение показали, что в параллельном режиме определенный запрос будет выполнять быстрее. Дополнительные сведения см. в разделе [Практическое руководство. Указание режима выполнения в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
## <a name="degree-of-parallelism"></a>Степень параллелизма  
 По умолчанию PLINQ использует все процессоры на главном компьютере. Можно указать PLINQ использовать не более указанного количества процессоров с помощью <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A> метод. Это пригодится в том случае, если вам нужно, чтобы другие процессы, выполняемые на том же компьютере, получали определенное количество процессорного времени. Следующий фрагмент кода позволяет запросу использовать не более двух процессоров.  
  
 [!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
 [!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]  
  
 В случаях, когда запрос выполняет значительный объем работы, не связанной с вычислениями, такой как ввод-вывод файлов, степень параллелизма может быть больше количества ядер на соответствующем компьютере.  
  
## <a name="ordered-versus-unordered-parallel-queries"></a>Упорядоченные и неупорядоченные параллельные запросы  
 В некоторых случаях оператор запроса должен выдавать результаты с сохранением порядка исходной последовательности. Язык PLINQ предоставляет <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> оператор для этой цели. <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>отличается от <xref:System.Linq.ParallelEnumerable.AsSequential%2A>. <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> Последовательности по-прежнему обрабатывать параллельно, но ее результаты буферизуются и сортируются. Поскольку сохранение порядка обычно включает дополнительную работу, <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> последовательности может обрабатываться медленнее, чем значение по умолчанию <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> последовательности. Будет ли та или иная упорядоченная параллельная операция выполняться быстрее, чем ее последовательная версия, зависит от многих факторов.  
  
 В следующем примере кода показано, как разрешить сохранение порядка.  
  
 [!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
 [!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]  
  
 Дополнительные сведения см. в разделе [Сохранение порядка в PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## <a name="parallel-vs-sequential-queries"></a>Сравнение параллельных и последовательных запросов  
 Некоторые операции требуют, чтобы исходные данные доставлялись последовательно. <xref:System.Linq.ParallelEnumerable> Запроса операторы переведен в последовательный режим автоматически по мере необходимости. Для определяемых пользователем операторах и пользовательских делегатов, требующих последовательного выполнения, PLINQ предоставляет <xref:System.Linq.ParallelEnumerable.AsSequential%2A> метод. При использовании <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, все последующие операторы в запросе выполняются последовательно до <xref:System.Linq.ParallelEnumerable.AsParallel%2A> будет вызван повторно. Дополнительные сведения см. в разделе [Практическое руководство. Объединение параллельных и последовательных запросов LINQ](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md).  
  
## <a name="options-for-merging-query-results"></a>Параметры для слияния результатов запроса  
 При параллельном выполнении запроса PLINQ его результаты из каждого рабочего потока должны быть снова объединены с основным потоком для использования циклом `foreach` (`For Each` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) либо вставки в список или массив. В некоторых случаях может быть полезно указать конкретный вид операции слияния, например для того, чтобы получать результаты быстрее. Для этой цели PLINQ поддерживает <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> метода и <xref:System.Linq.ParallelMergeOptions> перечисления. Дополнительные сведения см. в разделе [Параметры слияние в PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
## <a name="the-forall-operator"></a>Оператор ForAll  
 В последовательных [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] запросов, выполнение откладывается, пока запрос перечислен в `foreach` (`For Each` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) цикл или путем вызова метода, таких как <xref:System.Linq.ParallelEnumerable.ToList%2A> , <xref:System.Linq.ParallelEnumerable.ToArray%2A> , или <xref:System.Linq.ParallelEnumerable.ToDictionary%2A>. Кроме того, для выполнения запроса и итерации результатов в PLINQ можно использовать `foreach`. При этом сам оператор `foreach` параллельно не выполняется, а значит результаты всех параллельных задач необходимо снова объединить с тем потоком, в котором выполняется цикл. Оператор `foreach` можно использовать в PLINQ, если вам нужно сохранить окончательный порядок результатов запроса, а также при любой последовательной обработке результатов (например, при вызове `Console.WriteLine` для каждого элемента). Для выполнения запроса, когда сохранение порядка не требуется и обработка результатов может выполняться параллельно, используйте <xref:System.Linq.ParallelEnumerable.ForAll%2A> метод для выполнения запроса PLINQ. <xref:System.Linq.ParallelEnumerable.ForAll%2A>не выполняет этот заключительный шаг слияния. В следующем примере кода показано применение метода <xref:System.Linq.ParallelEnumerable.ForAll%2A>. <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>Здесь используется протокол, оптимизированный для добавлять несколько потоков параллельно без попытки удалить все элементы.  
  
 [!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
 [!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]  
  
 Ниже показано различие между `foreach` и <xref:System.Linq.ParallelEnumerable.ForAll%2A> по выполнению запроса.  
  
 ![Сравнение ForAll и ForEach](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS_ISVNT_ALLvsEACH")  
  
## <a name="cancellation"></a>Отмена  
 PLINQ интегрирован с типами отмены в [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. (Дополнительные сведения см. в разделе [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md).) Это значит, что в отличие от последовательных запросов LINQ to Objects запросы PLINQ можно отменять. Чтобы создать отменяемый запрос PLINQ, используйте <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> оператора на основе запроса и укажите <xref:System.Threading.CancellationToken> экземпляр в качестве аргумента. Когда <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> на маркере задано значение true, PLINQ отметит это, остановит обработку всех потоков и throw <xref:System.OperationCanceledException>.  
  
 Существует вероятность, что запрос PLINQ продолжит обработку некоторых элементов после того, как будет задан маркер отмены.  
  
 Для повышения скорости реагирования можно также отвечать на запросы отмены в пользовательских делегатах, выполняемых долгое время. Дополнительные сведения см. в разделе [Практическое руководство. Отмена запроса PLINQ](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md).  
  
## <a name="exceptions"></a>Исключения  
 При выполнении запроса PLINQ могут быть одновременно выданы сразу несколько исключений из разных потоков. Кроме того, код для обработки исключения может находиться не в том потоке, где находится код, который вызвал исключение. PLINQ использует <xref:System.AggregateException> введите для инкапсуляции все исключения, которые были созданы по запросу и упаковать эти исключения обратно в вызывающий поток. В вызывающем потоке должен присутствовать только один блок try-catch. Однако можно организовать итерацию всех исключений, которые содержатся в <xref:System.AggregateException> и catch, можно безопасно восстановиться. В редких случаях некоторые могут быть исключения, не упаковываются в <xref:System.AggregateException>, и <xref:System.Threading.ThreadAbortException>s также не заключены в оболочку.  
  
 Если исключения могут всплывать обратно в присоединяемый поток, запрос может продолжить обработку некоторых элементов после создания исключения.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Обработка исключений в запросе PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="custom-partitioners"></a>Пользовательские разделители  
 В некоторых случаях производительность запросов можно улучшить, написав пользовательский модуль разделения, который использует преимущества некоторых характеристик исходных данных. В запросе сам пользовательский модуль разделения является запрашиваемым перечислимым объектом.  
  
 [!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
 [!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]  
  
 PLINQ поддерживает фиксированное количество разделов (хотя для балансировки нагрузки данные могут динамически переназначаться этим разделам во время выполнения). <xref:System.Threading.Tasks.Parallel.For%2A>и <xref:System.Threading.Tasks.Parallel.ForEach%2A> поддерживают только динамическое секционирование, которое означает, что количество частей изменяется во время выполнения. Дополнительные сведения см. в разделе [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="measuring-plinq-performance"></a>Измерение производительности PLINQ  
 Во многих случаях запрос может выполняться параллельно, но на настройку параллельного запроса уходит больше времени, чем будет выиграно в результате. Если запрос не выполняет большой объем вычислений или источник данных небольшой, запрос PLINQ может быть медленнее, чем последовательный запрос LINQ to Objects. Анализатор параллельной производительности в Visual Studio Team Server позволяет сравнивать производительность различных запросов и таким образом выявлять проблемы обработки и определять, выполняется ли запрос параллельно или последовательно. Дополнительные сведения см. в разделах [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer) и [Практическое руководство. Измерение производительности запросов PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## <a name="see-also"></a>См. также  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)
