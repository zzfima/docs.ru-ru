---
title: Классификация стандартных операторов запросов по способу выполнения
ms.date: 07/20/2015
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
ms.openlocfilehash: edace870ea684c70bbf2768c44388f2236622c2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345713"
---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>Classification of Standard Query Operators by Manner of Execution (Visual Basic)
В реализации LINQ to Objects выполнение методов стандартных операторов запросов бывает немедленным и отложенным. Операторы запросов, использующие отложенное выполнение, можно дополнительно разделить на две категории: потоковые и непотоковые. Если вы знаете, каким образом выполняются разные операторы запросов, это может помочь понять результаты, полученные из данного запроса. Это особенно справедливо при изменении источника данных или создании одного запроса поверх другого. В этом разделе представлена классификация стандартных операторов запросов по способу выполнения.  
  
## <a name="manners-of-execution"></a>Способ выполнения  
  
### <a name="immediate"></a>Интерпретация  
 Немедленное выполнение означает, что источник данных считывается и операция выполняется в той точке кода, где объявлен запрос. Все стандартные операторы запросов, возвращающие один, неперечислимый результат, выполняются немедленно.  
  
### <a name="deferred"></a>Отложено  
 Отложенное выполнение означает, что операция не выполняется в той точке кода, где объявлен запрос. Она выполняется только после перечисления переменной запроса, например с помощью оператора `For Each`. Это означает, что результаты выполнения запроса зависят от содержимого источника данных при выполнении запроса, а не при его определении. Если переменная запроса перечисляется несколько раз, результаты могут каждый раз отличаться. Практически все стандартные операторы запроса, которые возвращают значения типа <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IOrderedEnumerable%601>, выполняются отложенным способом.  
  
 Операторы запросов, использующие отложенное выполнение, можно дополнительно разделить на потоковые и непотоковые.  
  
#### <a name="streaming"></a>Потоковые операторы  
 Потоковые операторы не считывают все исходные данные до создания элементов. Во время выполнения потоковый оператор выполняет свою операцию с каждым исходным элементом по мере считывания и при необходимости создает элемент. Потоковый оператор продолжает считывание исходных элементов до того момента, когда можно будет создать итоговый элемент. Это означает, что для получения одного итогового элемента может быть считано несколько исходных элементов.  
  
#### <a name="non-streaming"></a>Непотоковые  
 Непотоковые операторы должны считать все исходные данные до создания итогового элемента. В эту категорию попадают операции сортировки и группировки. Во время выполнения непотоковые операторы запросов считывают все исходные данные, помещают их в структуру данных, выполняют операцию и создают итоговые элементы.  
  
## <a name="classification-table"></a>Таблица классификации  
 В следующей таблице приведена классификация всех методов стандартных операторов запросов по способу выполнения.  
  
> [!NOTE]
> Если оператор помечен в двух столбцах, в операции участвуют две входные последовательности, и каждая последовательность вычисляется по-разному. В таких случаях первая последовательность в списке параметров всегда вычисляется отложенным потоковым способом.  
  
|Стандартный оператор запроса|Тип возвращаемого значения|Немедленное выполнение|Отложенное потоковое выполнение|Отложенное непотоковое выполнение|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Average%2A>|Одно числовое значение|x|||  
|<xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32>|x|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.ElementAt%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601>|x|||  
|<xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.First%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|x|  
<xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.Last%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64>|x|||  
|<xref:System.Linq.Enumerable.Max%2A>|Одно числовое значение, TSource или TResult|x|||  
|<xref:System.Linq.Enumerable.Min%2A>|Одно числовое значение, TSource или TResult|x|||  
|<xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Single%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Sum%2A>|Одно числовое значение|x|||  
|<xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
<xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.ToArray%2A>|Массив TSource|x|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602>|x|||  
|<xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601>|x|||  
|<xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602>|x|||  
|<xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.Enumerable>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
