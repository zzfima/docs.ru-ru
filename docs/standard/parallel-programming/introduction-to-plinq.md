---
title: "Introduction to PLINQ | Microsoft Docs"
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
  - "PLINQ queries, introduction to"
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Introduction to PLINQ
## Параллельный запрос  
 LINQ был впервые представлен в [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].  Он предполагает унифицированную модель для запросов к любому источнику данных <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> типобезопасным образом.  LINQ to Objects — это имя запросов LINQ, которые выполняются в коллекциях в памяти, например <xref:System.Collections.Generic.List%601> и массивы.  В данной статье предполагается, что пользователь имеет базовые знания по LINQ.  Для получения дополнительной информации см. [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).  
  
 Параллельный LINQ \(PLINQ\) является параллельной реализацией шаблона LINQ.  Запрос PLINQ во многом напоминает непараллельный запрос LINQ to Objects.  Запросы PLINQ, так же как последовательные запросы [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)], работают в любом источнике данных <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> в памяти и имеют возможность отложенного выполнения, т. е. они не начинают выполняться, пока запрос не перечислен.  Основным различием является то, что PLINQ пытается полностью использовать возможности всех процессоров в системе.  Это достигается путем разделения источника данных на сегменты и параллельного выполнения запроса каждого сегмента в отдельном рабочем потоке на нескольких процессорах.  Во многих случаях параллельное выполнение означает, что запрос выполняется значительно быстрее.  
  
 Благодаря параллельному выполнению PLINQ может значительно увеличить производительность по сравнению с устаревшим кодом для определенных типов запросов часто просто путем добавления операции запроса <xref:System.Linq.ParallelEnumerable.AsParallel%2A> к источнику данных.  Однако параллелизм может привести к появлению собственных сложностей, и не все операции запросов выполняются быстрее в PLINQ.  В действительности, параллелизация фактически замедляет выполнение определенных запросов.  Таким образом, следует понимать влияние различных проблем, например упорядочения, на параллельные запросы.  Для получения дополнительной информации см. [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
> [!NOTE]
>  В этой документации для определения делегатов в PLINQ используются лямбда\-выражения.  Сведения о лямбда\-выражениях в C\# или Visual Basic см. в разделе [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 Далее в статье приводится обзор основных классов PLINQ и способы создания запросов PLINQ.  В каждом разделе содержатся ссылки на более подробные сведения и примеры кода.  
  
## Класс ParallelEnumerable  
 Класс <xref:System.Linq.ParallelEnumerable?displayProperty=fullName> предоставляет практически все функциональные возможности PLINQ.  Он и остальные типы пространства имен <xref:System.Linq?displayProperty=fullName> компилируются в сборку System.Core.dll.  Проекты C\# и Visual Basic по умолчанию в Visual Studio ссылаются на эту сборку и импортируют пространство имен.  
  
 Класс <xref:System.Linq.ParallelEnumerable> включает реализации всех стандартных операторов запросов, поддерживаемых LINQ to Objects, хотя он предпринимает попытки параллелизации каждого из них.  Дополнительные сведения о [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] см. в разделе [Introduction to LINQ](../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
 Помимо стандартных операторов запросов класс <xref:System.Linq.ParallelEnumerable> содержит набор методов, которые обеспечивают поведения, характерные для параллельного выполнения.  Эти характерные для PLINQ методы перечислены в следующей таблице.  
  
|Оператор ParallelEnumerable|Описание|  
|---------------------------------|--------------|  
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|Точка входа для PLINQ.  Указывает на необходимость параллелизации остальной части запроса, если это возможно.|  
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|Указывает на необходимость последовательного выполнения остальной части запроса как непараллельного запроса LINQ.|  
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|Указывает, что PLINQ должен сохранить порядок исходной последовательности для остальной части запроса или до тех пор, пока порядок не будет изменен, например с помощью предложения orderby \(Order By в Visual Basic\).|  
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|Указывает, что PLINQ не должен сохранять порядок исходной последовательности для остальной части запроса.|  
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|Указывает, что PLINQ должен периодически отслеживать состояние предоставленного токена отмены и отменять выполнение при запросе.|  
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|Указывает максимальное количество процессоров, которое должен использовать PLINQ для параллелизации запроса.|  
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|Предоставляет подсказку о том, как PLINQ должен, если это возможно, выполнять слияние параллельных результатов в одну последовательность в потоке\-потребителе.|  
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|Указывает, должен ли PLINQ выполнять параллелизацию запроса, даже если согласно поведению по умолчанию он будет выполняться последовательно.|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Многопоточный метод перечисления, который в отличие от итерации результатов запроса позволяет обрабатывать результаты параллельно без предварительного слияния в поток\-потребитель.|  
|Перегрузка <xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Уникальная для PLINQ перегрузка, обеспечивающая промежуточное агрегирование локальных частей потока, и предоставляющая функцию окончательного агрегирования для объединения результатов всех частей.|  
  
## Модель, включаемая по требованию  
 При написании запроса включается в PLINQ путем вызова метода расширения <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName> в источнике данных, как показано в следующем примере.  
  
 [!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
 [!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]  
  
 Метод расширения <xref:System.Linq.ParallelEnumerable.AsParallel%2A> связывает последующие операторы запросов, в этом случае `where` и `select`, с реализациями <xref:System.Linq.ParallelEnumerable?displayProperty=fullName>.  
  
## Режимы выполнения  
 По умолчанию PLINQ является консервативным.  Во время выполнения инфраструктура PLINQ анализирует общую структуру запроса.  Если выполнение запроса скорее всего ускорится за счет параллелизации, PLINQ разделяет исходную последовательность на задачи, которые могут выполняться одновременно.  Если выполнять параллелизацию запроса небезопасно, PLINQ просто выполняет запрос последовательно.  Если PLINQ может выбирать между алгоритмом параллельной обработки, который потенциально требует больших затрат ресурсов, и алгоритмом последовательной обработки, не требующим больших затрат ресурсов, он выбирает алгоритм последовательной обработки по умолчанию.  Чтобы указать PLINQ выбрать алгоритм параллельной обработки, можно использовать метод <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> и перечисление <xref:System.Linq.ParallelExecutionMode?displayProperty=fullName>.  Это полезно, если тестирование и измерение показали, что определенный запрос будет выполнять быстрее параллельно.  Для получения дополнительной информации см. [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
## Степень параллелизма  
 По умолчанию PLINQ использует все процессоры на главном компьютере до 64.  Можно указать PLINQ использовать не более указанного количества процессоров с помощью метода <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>.  Это полезно, когда требуется убедиться, что другие процессы, выполняющиеся на компьютере, получают определенное количество времени ЦП.  В следующем фрагменте запрос ограничивается использованием не более двух процессоров.  
  
 [!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
 [!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]  
  
 В случаях, когда запрос выполняет значительный объем работы, не ограниченной по скорости вычислений, например файловый ввод\-вывод, может быть полезно указать степень параллелизма больше, чем количество ядер в компьютере.  
  
## Упорядоченные и неупорядоченные параллельные запросы  
 В некоторых запросах оператор запроса должен производить результаты с сохранением порядка исходной последовательности.  Для этой цели PLINQ предоставляет оператор <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> отличается от <xref:System.Linq.ParallelEnumerable.AsSequential%2A>.  Последовательность <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> по\-прежнему обрабатывается параллельно, но ее результаты буферизуются и сортируются.  Поскольку сохранение порядка обычно включает дополнительную работу, последовательность <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> может обрабатываться медленнее, чем последовательность <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> по умолчанию.  Является ли определенная упорядоченная параллельная операция быстрее, чем последовательная, зависит от многих факторов.  
  
 В следующем примере кода показано, как использовать сохранение порядка.  
  
 [!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
 [!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]  
  
 Для получения дополнительной информации см. [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## Сравнение параллельных и последовательных запросов  
 Некоторые операции требуют доставки исходных данных последовательным образом.  Операторы запроса <xref:System.Linq.ParallelEnumerable> осуществляют возврат к последовательному режиму автоматически при необходимости.  Для определяемых пользователем операторов запроса и пользовательских делегатов, требующих последовательного выполнения, PLINQ предоставляет метод <xref:System.Linq.ParallelEnumerable.AsSequential%2A>.  При использовании метода <xref:System.Linq.ParallelEnumerable.AsSequential%2A> все последующие операторы в запросе выполняются последовательно до повторного вызова метода <xref:System.Linq.ParallelEnumerable.AsParallel%2A>.  Для получения дополнительной информации см. [How to: Combine Parallel and Sequential LINQ Queries](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md).  
  
## Параметры для слияния результатов запроса  
 При параллельном выполнении запроса PLINQ его результаты из каждого рабочего потока должны быть объединены обратно в основном потоке для использования циклом `foreach` \(`For Each` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) либо вставки в список или массив.  В некоторых случаях может быть полезно указать определенный вид операции слияния, например для начала более быстрого производства результатов.  Для этого PLINQ поддерживает метод <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> и перечисление <xref:System.Linq.ParallelMergeOptions>.  Для получения дополнительной информации см. [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
## Оператор ForAll  
 В последовательных запросах [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] выполнение откладывается, пока запрос не будет перечислен либо в цикле `foreach` \(`For Each` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), либо путем вызова метода, например <xref:System.Linq.ParallelEnumerable.ToList%2A>, <xref:System.Linq.ParallelEnumerable.ToArray%2A> или <xref:System.Linq.ParallelEnumerable.ToDictionary%2A>.  В PLINQ также можно использовать `foreach` для выполнения запроса и итерации результатов.  Однако сам оператор `foreach` не выполняется параллельно, и поэтому требуется объединить выходные данные всех параллельных задач обратно в потоке, в котором выполняется цикл.  В PLINQ оператор `foreach` можно использовать, если необходимо сохранить окончательный порядок результатов запроса, а также при каждой обработке результатов последовательным образом, например при вызове `Console.WriteLine` для каждого элемента.  Для более быстрого выполнения запроса в случаях, когда сохранение порядка не требуется и непосредственно обработка результатов может выполняться параллельно, используйте метод <xref:System.Linq.ParallelEnumerable.ForAll%2A> для выполнения запроса PLINQ.  <xref:System.Linq.ParallelEnumerable.ForAll%2A> не выполняет этот заключительный шаг слияния.  В следующем примере кода показано, как использовать метод <xref:System.Linq.ParallelEnumerable.ForAll%2A>.  <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> используется здесь, потому что он оптимизирован для нескольких потоков, добавляя параллельность без попытки удалить элементы.  
  
 [!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
 [!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]  
  
 На следующем рисунке показано различие между `foreach` и <xref:System.Linq.ParallelEnumerable.ForAll%2A> по выполнению запроса.  
  
 ![Сравнение ForAll и ForEach](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS\_ISVNT\_ALLvsEACH")  
  
## Отмена  
 PLINQ интегрирован с типами отмены в [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. \(Дополнительные сведения см. в разделе [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).\) Таким образом, в отличие от последовательных запросов LINQ to Objects, запросы PLINQ можно отменить.  Чтобы создать отменяемый запрос PLINQ, используйте оператор <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> запроса и предоставьте экземпляр <xref:System.Threading.CancellationToken> в качестве аргумента.  Если свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> токена имеет значение true, PLINQ отметит это, остановит обработку всех потоков и создаст исключение <xref:System.OperationCanceledException>.  
  
 Запрос PLINQ может продолжить обрабатывать некоторые элементы после задания токена отмены.  
  
 Чтобы увеличить скорость ответа, также можно отвечать на запросы отмены в длительных пользовательских делегатах.  Для получения дополнительной информации см. [How to: Cancel a PLINQ Query](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md).  
  
## Исключения  
 При выполнении запроса PLINQ может быть создано несколько исключений из разных потоков одновременно.  Кроме того, код для обработки исключения может находиться не в том потоке, в котором код создал данное исключение.  PLINQ использует тип <xref:System.AggregateException> для инкапсуляции всех исключений, созданных запросом, и маршалинга этих исключений в вызывающем потоке.  В вызывающем потоке необходим только один блок try\-catch.  Однако можно выполнить итерацию всех исключений, инкапсулированных в <xref:System.AggregateException>, и перехватить любое исключение, из которого можно выполнить безопасное восстановление.  В редких случаях могут быть созданы некоторые исключения, которые не заключены в <xref:System.AggregateException>, и исключения <xref:System.Threading.ThreadAbortException> также не заключаются в оболочку.  
  
 Если позволить исключениям маршрутизироваться по восходящей обратно в присоединяемый поток, запрос может продолжить обработку некоторых элементов после создания исключения.  
  
 Для получения дополнительной информации см. [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## Пользовательские модули разделения  
 В некоторых случаях можно улучшить производительность, написав пользовательские модули разделения, которые используют преимущества некоторых характеристик исходных данных.  В запросе сам пользовательский модуль разделения является запрашиваемым перечисляемым объектом.  
  
 [!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
 [!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]  
  
 PLINQ поддерживает фиксированное количество частей \(хотя данные могут быть динамически переназначены этим частям во время выполнения для балансировки нагрузки\).  Методы <xref:System.Threading.Tasks.Parallel.For%2A> и <xref:System.Threading.Tasks.Parallel.ForEach%2A> поддерживают только динамическое разделение, т. е. количество частей изменяется во время выполнения.  Для получения дополнительной информации см. [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## Измерение производительности PLINQ  
 Во многих случаях запрос можно обработать параллельно, но нагрузка при настройке параллельного запроса сводит на нет полученный выигрыш в производительности.  Если в запросе не выполняется много вычислений или источник данных небольшой, запрос PLINQ может выполняться медленнее, чем последовательный запрос LINQ to Objects.  Анализатор параллельной производительности в Visual Studio Team Server позволяет сравнить производительность различных запросов, чтобы обнаружить узкие места обработки и определить, выполняется ли запрос параллельно или последовательно.  Дополнительные сведения см. в разделах [Визуализатор параллелизма](../Topic/Concurrency%20Visualizer.md) и [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)