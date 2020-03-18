---
title: Классификация стандартных операторов запросов по способу выполнения (C#)
ms.date: 07/20/2015
ms.assetid: b9435ce5-a7cf-4182-9f01-f3468a5533dc
ms.openlocfilehash: ccf8fced5c92ceaaf84f9240e235da0e2b56ac1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69924290"
---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-c"></a>Классификация стандартных операторов запросов по способу выполнения (C#)
В реализации LINQ to Objects выполнение методов стандартных операторов запросов бывает немедленным и отложенным. Операторы запросов, использующие отложенное выполнение, можно дополнительно разделить на две категории: потоковые и непотоковые. Если вы знаете, каким образом выполняются разные операторы запросов, это может помочь понять результаты, полученные из данного запроса. Это особенно справедливо при изменении источника данных или создании одного запроса поверх другого. В этом разделе представлена классификация стандартных операторов запросов по способу выполнения.  
  
## <a name="manners-of-execution"></a>Способ выполнения  
  
### <a name="immediate"></a>Немедленно  
 Немедленное выполнение означает, что источник данных считывается и операция выполняется в той точке кода, где объявлен запрос. Все стандартные операторы запросов, возвращающие один, неперечислимый результат, выполняются немедленно.  
  
### <a name="deferred"></a>Отложено  
 Отложенное выполнение означает, что операция не выполняется в той точке кода, где объявлен запрос. Она выполняется только после перечисления переменной запроса, например с помощью оператора `foreach`. Это означает, что результаты выполнения запроса зависят от содержимого источника данных при выполнении запроса, а не при его определении. Если переменная запроса перечисляется несколько раз, результаты могут каждый раз отличаться. Практически все стандартные операторы запроса, которые возвращают значения типа <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IOrderedEnumerable%601>, выполняются отложенным способом.  
  
 Операторы запросов, использующие отложенное выполнение, можно дополнительно разделить на потоковые и непотоковые.  
  
#### <a name="streaming"></a>Потоковая передача  
 Потоковые операторы не считывают все исходные данные до создания элементов. Во время выполнения потоковый оператор выполняет свою операцию с каждым исходным элементом по мере считывания и при необходимости создает элемент. Потоковый оператор продолжает считывание исходных элементов до того момента, когда можно будет создать итоговый элемент. Это означает, что для получения одного итогового элемента может быть считано несколько исходных элементов.  
  
#### <a name="non-streaming"></a>Непотоковые  
 Непотоковые операторы должны считать все исходные данные до создания итогового элемента. В эту категорию попадают операции сортировки и группировки. Во время выполнения непотоковые операторы запросов считывают все исходные данные, помещают их в структуру данных, выполняют операцию и создают итоговые элементы.  
  
## <a name="classification-table"></a>Таблица классификации  
 В следующей таблице приведена классификация всех методов стандартных операторов запросов по способу выполнения.  
  
> [!NOTE]
> Если оператор помечен в двух столбцах, в операции участвуют две входные последовательности, и каждая последовательность вычисляется по-разному. В таких случаях первая последовательность в списке параметров всегда вычисляется отложенным потоковым способом.  
  
|Стандартный оператор запроса|Тип возвращаемого значения|Немедленное выполнение|Отложенное потоковое выполнение|Отложенное непотоковое выполнение|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Average%2A>|Одно числовое значение|X|||  
|<xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32>|X|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ElementAt%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601>|X|||  
|<xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.First%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
<xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Last%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64>|X|||  
|<xref:System.Linq.Enumerable.Max%2A>|Одно числовое значение, TSource или TResult|X|||  
|<xref:System.Linq.Enumerable.Min%2A>|Одно числовое значение, TSource или TResult|X|||  
|<xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Single%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Sum%2A>|Одно числовое значение|X|||  
|<xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
<xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ToArray%2A>|Массив TSource|X|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602>|X|||  
|<xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601>|X|||  
|<xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602>|X|||  
|<xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Linq.Enumerable>
- [Общие сведения о стандартных операторах запроса (C#)](./standard-query-operators-overview.md)
- [Синтаксис выражений запроса для стандартных операторов запроса (C#)](./query-expression-syntax-for-standard-query-operators.md)
- [LINQ to Objects (C#)](./linq-to-objects.md)
