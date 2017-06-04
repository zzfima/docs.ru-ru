---
title: "Order Preservation in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, order preservation"
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Order Preservation in PLINQ
Цель PLINQ — максимально повысить производительность при сохранении правильности.  Запрос должен выполняться как можно быстрее, но по\-прежнему выдавать правильные результаты.  В некоторых случаях для поддержания правильности требуется сохранить порядок исходной последовательности. Однако для этого могут потребоваться большие затраты компьютерных ресурсов.  Таким образом, по умолчанию в PLINQ не сохраняется порядок исходной последовательности.  В этом отношении PLINQ напоминает [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], но не похож на запрос LINQ to Objects, в котором порядок сохраняется.  
  
 Чтобы переопределить поведение по умолчанию, можно включить сохранение порядка в исходной последовательности с помощью оператора <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  Сохранение порядка можно отключить позже в запросе с помощью метода <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>.  Запрос обрабатывается обоими методами на основании эвристики, определяющей необходимость параллельного или последовательного выполнения запроса.  Для получения дополнительной информации см. [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
 В следующем примере показан неупорядоченный параллельный запрос, который выполняет фильтрацию для всех элементов, соответствующих условию, не пытаясь упорядочить результаты каким\-либо образом.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 В ответ на этот запрос не обязательно выдаются первые 1000 городов в исходной последовательности, которые удовлетворяют условию, вместо этого выдается некоторый набор из 1000 городов, удовлетворяющих условию.  Операторы запроса PLINQ разделяют исходную последовательность на несколько подпоследовательностей, которые обрабатываются как одновременные задачи.  Если сохранение порядка не задано, результаты из каждой части передаются на следующий этап запроса в произвольном порядке.  Кроме того, разделение может привести к созданию подмножества результатов до того, как начнется обработка оставшихся элементов.  Полученный порядок может каждый раз отличаться.  Приложение не может управлять эти процессом, поскольку оно зависит от того, как операционная система планирует потоки.  
  
 В следующем примере переопределяется поведение по умолчанию в исходной последовательности с помощью оператора <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  Это гарантирует возврат методом <xref:System.Linq.ParallelEnumerable.Take%2A> первых 1000 городов в исходной последовательности, отвечающих условию.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Однако этот запрос, возможно, не выполняется так же быстро, как неупорядоченная версия, поскольку в нем должен отслеживаться исходный порядок во всех частях исходной последовательности и во время слияния обеспечиваться соответствующий порядок.  Следовательно, метод <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> рекомендуется использовать только при необходимости и только для тех частей запроса, которые его требуют.  Если сохранение порядка больше не требуется, используйте метод <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> для его отключения.  В следующем примере это достигается путем создания двух запросов.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Обратите внимание, что в PLINQ сохраняется порядок последовательности, созданный с помощью операторов порядка для остальной части запроса.  Другими словами, операторы, такие как <xref:System.Linq.ParallelEnumerable.OrderBy%2A> и <xref:System.Linq.ParallelEnumerable.ThenBy%2A>, обрабатываются, как если бы за ними следовал вызов метода <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
## Операторы запросов и упорядочение  
 Следующие операторы запросов обеспечивают сохранение порядка во всех последующих операциях в запросе или до тех пор, пока не вызывается метод <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>.  
  
-   <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 Следующие операторы запросов PLINQ могут в некоторых случаях требовать выдачи правильных результатов упорядоченных исходных последовательностей.  
  
-   <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Поведение некоторых операторов запросов PLINQ отличается в зависимости от того, является их исходная последовательность упорядоченной или неупорядоченной.  Эти операторы перечислены в следующей таблице.  
  
|Оператор|Результат при упорядоченной исходной последовательности|Результат при неупорядоченной исходной последовательности|  
|--------------|-------------------------------------------------------------|---------------------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|Неупорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Выполняется недетерминированно параллельно|Выполняется недетерминированно параллельно|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|Переупорядочивает последовательность|Запускает новую упорядоченную часть|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|Переупорядочивает последовательность|Запускает новую упорядоченную часть|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|Неприменимо \(такое же значение по умолчанию, что и <xref:System.Linq.ParallelEnumerable.AsParallel%2A>\)|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|Неприменимо \(такое же значение по умолчанию, как <xref:System.Linq.ParallelEnumerable.AsParallel%2A>\)|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Изменяет порядок на обратный|Не выполняет действий|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Select%2A> \(индексирован\)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A> \(индексирован\)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Упорядоченное сравнение|Неупорядоченное сравнение|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Пропускает первые *n* элементов|Пропускает любые *n* элементов|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Упорядоченные результаты|Недетерминированный.  Выполняет метод SkipWhile для текущего произвольного порядка|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Принимает первые элементы в количестве `n`|Принимает любые элементы в количестве `n`|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Упорядоченные результаты|Недетерминированный.  Выполняет метод TakeWhile для текущего произвольного порядка|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Дополняет метод `OrderBy`|Дополняет метод `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Дополняет метод `OrderBy`|Дополняет метод `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Where%2A> \(индексирован\)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
  
 Неупорядоченные результаты активно не перемешиваются, к ним просто не применяется никакая особая логика сортировки.  В некоторых случаях неупорядоченный запрос может сохранять порядок исходной последовательности.  Для запросов, использующих индексированный оператор Select, PLINQ всегда выводит выходные элементы в порядке возрастания индексов, однако не гарантирует, какие индексы для каких элементов будут назначены.  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)