---
title: Сохранение порядка в PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
ms.openlocfilehash: 5b067fa277816e6105d37047c6c4996a4cbb9b5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138223"
---
# <a name="order-preservation-in-plinq"></a>Сохранение порядка в PLINQ
PLINQ предназначен для повышения производительности при сохранении правильности вычислений. Запрос должен выполняться как можно быстрее, но всегда давать правильные результаты. В некоторых случаях для правильных расчетов нужно соблюдать порядок исходной последовательности, но упорядочение может требовать больших вычислительных ресурсов. Поэтому по умолчанию PLINQ не сохраняет порядок исходной последовательности. В этом PLINQ похож на [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], но отличается от LINQ to Objects, который строго сохраняет порядок.  
  
 Чтобы переопределить поведение по умолчанию, можно принудительно затребовать сохранение порядка, указав оператор <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> в исходной последовательности. Сохранение порядка в запросе в последующих частях запроса можно отключить с помощью метода <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>. В обоих случаях запрос обрабатывается с учетом эвристического анализа, который выбирает параллельный или последовательный режим обработки. Дополнительные сведения см. в разделе [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
 Следующий пример демонстрирует неупорядоченный параллельный запрос, который отбирает все соответствующие условию элементы, не пытаясь упорядочивать результаты.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 Этот запрос не всегда возвращает первые 1000 городов из исходной последовательности, которые отвечают условию, а просто некоторый набор из 1000 подходящих городов. Операторы запроса PLINQ разделяют исходную последовательность на несколько подпоследовательностей и обрабатывают их как одновременные задачи. Если сохранение порядка не требуется, результаты из каждого сегмента передаются на следующий этап обработки в произвольном порядке. Кроме того, поток обработки сегмента может возвращать подмножество результатов раньше, чем продолжит обработку следующих элементов. Порядок полученных результатов будет разным при каждом выполнении. Приложение не может контролировать результат, поскольку он зависит от распределения потоков в операционной системе.  
  
 В следующем примере поведение по умолчанию переопределяется путем включения оператора <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> в исходную последовательность. Это гарантирует, что метод <xref:System.Linq.ParallelEnumerable.Take%2A> всегда возвращает первые 1000 подходящих городов из исходной последовательности.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Однако этот запрос, скорее всего, выполняется медленнее неупорядоченной версии, так как он должен отслеживать исходный порядок во всех сегментах и контролировать его во время слияния. Поэтому мы рекомендуем использовать <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> только при реальной необходимости и только для тех частей запроса, в которых нужен строгий порядок. Когда сохранение порядка больше не требуется, отключите его с помощью <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>. В следующем примере мы создаем для этого два запроса.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Обратите внимание, что в оставшейся части запроса PLINQ сохраняет порядок последовательности, созданный операторами с контролем порядка. Другими словами, операторы типа <xref:System.Linq.ParallelEnumerable.OrderBy%2A> и <xref:System.Linq.ParallelEnumerable.ThenBy%2A> обрабатываются так, как если бы после них стоял вызов <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
## <a name="query-operators-and-ordering"></a>Операторы запросов и упорядочение  
 Следующие операторы запроса налагают сохранение порядка на все последующие операции запроса, пока не встретится вызов <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>.  
  
- <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 Следующие операторы запроса PLINQ в некоторых случаях требуют упорядочения исходных последовательностей для получения правильных результатов.  
  
- <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
- <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Некоторые операторы запроса PLINQ ведут себя по-разному для упорядоченной и неупорядоченной исходной последовательности. Все они перечислены в следующей таблице.  
  
|Оператор|Результат для упорядоченной исходной последовательности|Результат для неупорядоченной исходной последовательности|  
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
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Недетерминированные результаты параллельного выполнения|Недетерминированные результаты параллельного выполнения|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|Возвращает указанный элемент|Произвольный элемент|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|Переупорядочивает последовательность|Начинает новый раздел с контролем порядка|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|Переупорядочивает последовательность|Начинает новый раздел с контролем порядка|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|Неприменимо (значение по умолчанию такое же, как для <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|Неприменимо (значение по умолчанию такое же, как для <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Изменяет порядок на обратный|Ничего не делает|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Select%2A> (индексированный)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A> (индексированный)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Упорядоченное сравнение|Неупорядоченное сравнение|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Пропускает первые *n* элементов|Пропускает любые *n* элементов|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Упорядоченные результаты|Недетерминированный результат. Выполняет метод SkipWhile для текущего произвольного порядка|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|Недетерминированные выходные данные для неассоциативных или некоммутативных операций|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Отбирает первые `n` элементов|Отбирает любые `n` элементов|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Упорядоченные результаты|Недетерминированный результат. Выполняет метод TakeWhile для текущего произвольного порядка|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Дополняет `OrderBy`|Дополняет `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Дополняет `OrderBy`|Дополняет `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|Неприменимо|Неприменимо|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Where%2A> (индексированный)|Упорядоченные результаты|Неупорядоченные результаты|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Упорядоченные результаты|Неупорядоченные результаты|  
  
 Неупорядоченные результаты не перемешиваются активно. Просто к ним не применяется логика для упорядочивания. В некоторых случаях неупорядоченный запрос может сохранять порядок исходной последовательности. Для запросов, использующих индексированный оператор Select, PLINQ гарантирует порядок возрастания индексов для выходных элементов, но не гарантирует конкретные индексы для этих элементов.  
  
## <a name="see-also"></a>См. также

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
