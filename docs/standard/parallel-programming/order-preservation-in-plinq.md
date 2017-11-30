---
title: "Сохранение порядка в PLINQ"
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
helpviewer_keywords: PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 060459cf8f408e40ddc394fbcda6a022ec6379de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="order-preservation-in-plinq"></a>Сохранение порядка в PLINQ
В PLINQ предназначена для повышения производительности при сохранении определения правильности. Запрос должен максимально возможной скоростью запуска, но по-прежнему выдавать правильные результаты. В некоторых случаях для поддержания правильности требуется заказ исходной последовательности должны быть сохранены; Однако упорядочение может быть требовательных к вычислительным ресурсам. Таким образом по умолчанию PLINQ не сохраняет порядок исходной последовательности. В этом отношении PLINQ напоминает [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], но в отличие от LINQ to Objects, которая сохранять порядок.  
  
 Чтобы переопределить поведение по умолчанию, можно включить сохранение порядка с помощью <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> оператор в исходной последовательности. Затем можно отключить сохранение порядка в запросе в дальнейшем с помощью <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> метод. В обоих случаях запрос обрабатывается основании эвристики, определить, следует ли выполнить запрос параллельно или последовательного. Дополнительные сведения см. в разделе [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
 В примере показан неупорядоченный параллельный запрос фильтрации для всех элементов, которые соответствуют условию, не пытаясь упорядочить результаты каким-либо образом.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 Этот запрос не обязательно выдаются первые 1000 городов в исходной последовательности, удовлетворяющих условию, но вместо некоторый набор из 1000 городов, удовлетворяющих условию. Операторы запроса PLINQ разделяют исходную последовательность на несколько подпоследовательностей, которые обрабатываются как одновременные задачи. Если сохранение порядка не указан, результаты из каждой части передаются на следующий этап запроса в произвольном порядке. Кроме того разделение может привести подмножества результатов, прежде чем он продолжает обрабатывать оставшиеся элементы. Полученный в результате порядок может отличаться каждый раз. Приложение не контролирует этот процесс, так как он зависит от того, каким образом операционная система планирует потоки.  
  
 В следующем примере переопределяется поведение по умолчанию с помощью <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> оператор в исходной последовательности. Это гарантирует, что <xref:System.Linq.ParallelEnumerable.Take%2A> метод возвращает первые 1000 городов в исходной последовательности, удовлетворяющих условию.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Однако этот запрос, скорее всего, не выполняется столь же быстро, как неупорядоченная версия, так как он должен отслеживать исходный порядок во всей секции и во время слияния убедиться, что порядок согласованы. Таким образом, мы рекомендуем использовать <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> только в том случае, если это требуется и только для тех частей запроса, которые их используют. Если сохранение порядка больше не требуется, используйте <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> ее выключения. Следующий пример это достигается путем создания двух запросов.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Обратите внимание, что PLINQ сохраняет порядок последовательности, созданный с помощью операторов порядка для остальной части запроса. Другими словами, операторы, такие как <xref:System.Linq.ParallelEnumerable.OrderBy%2A> и <xref:System.Linq.ParallelEnumerable.ThenBy%2A> обрабатываются, как если бы они были после вызова, чтобы <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
## <a name="query-operators-and-ordering"></a>Операторы запросов и упорядочение  
 Следующие операторы запросов обеспечивают сохранение порядка во всех последующих операциях в запросе или до <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> вызывается:  
  
-   <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 Следующие операторы запросов PLINQ может в некоторых случаях требуется упорядоченных исходных последовательностей для получения правильных результатов:  
  
-   <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Некоторые операторы запросов PLINQ ведут себя по-разному, в зависимости от того, упорядоченной или неупорядоченной их исходной последовательности. В следующей таблице перечислены эти операторы.  
  
|Оператор|Результат при упорядоченной исходной последовательности|Результат, если исходная последовательность не упорядочена|  
|--------------|------------------------------------------------|--------------------------------------------------|  
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
|<xref:System.Linq.ParallelEnumerable.Range%2A>|Неприменимо (по умолчанию, таким же как <xref:System.Linq.ParallelEnumerable.AsParallel%2A> )|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|Неприменимо (по умолчанию, таким же как <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Обращает|Ничего не делает|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>(индекс)|Упорядоченные результаты|Неупорядоченные результаты.|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Отсортированных результатов.|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>(индекс)|Отсортированных результатов.|Неупорядоченные результаты.|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Упорядоченное сравнение|Неупорядоченные сравнения|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Пропускает первые  *n*  элементов|Пропускает все  *n*  элементов|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Отсортированных результатов.|Недетерминированные. Выполняет метод SkipWhile для текущего произвольного порядка|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Принимает первый `n` элементов|Принимает любые `n` элементов|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Упорядоченные результаты|Недетерминированные. Выполняет метод TakeWhile для текущего произвольного порядка|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Дополнения`OrderBy`|Дополнения`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Дополнения`OrderBy`|Дополнения`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>(индекс)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
  
 Неупорядоченные результаты активно не перемешиваются; они просто не иметь любой специальную логику для упорядочивания, применяемый к ним. В некоторых случаях неупорядоченный запрос может сохранять порядок исходной последовательности. Для запросов, использующих индексированный оператор Select PLINQ гарантирует, что выходные элементы будет продвижением в порядке возрастания индексов, однако нет гарантии, какие индексы будут назначены какие элементы.  
  
## <a name="see-also"></a>См. также  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
