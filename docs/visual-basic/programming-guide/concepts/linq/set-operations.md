---
title: Операции над множествами
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: fe9d910415f30fe672dc702f719fdefdb9c0b3d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350619"
---
# <a name="set-operations-visual-basic"></a>Операции с наборами (Visual Basic)

Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).

Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.

## <a name="methods"></a>Методы

|Имя метода|Описание|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|
|-----------------|-----------------|------------------------------------------|----------------------|
|Distinct|Удаляет повторяющиеся значения из коллекции.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|Исключения|Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.|Неприменимо.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|Пересечение|Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.|Неприменимо.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|Объединение|Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.|Неприменимо.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a>Сравнение операций над множествами

### <a name="distinct"></a>Distinct

На следующем рисунке показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов. Возвращаемая последовательность содержит уникальные элементы из входной последовательности.

![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a>Исключения

На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.

![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")

### <a name="intersect"></a>Пересечение

На следующем рисунке показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.

![График, отображающий пересечение двух пакетов.](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a>Объединение

На следующем рисунке показана операция объединения двух последовательностей символов. Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.

![График, показывающий объединение двух последовательностей.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса

В следующем примере предложение `Distinct` в запросе LINQ используется для возврата уникальных чисел из списка целых чисел.

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Предложение Distinct](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Практические руководства. объединение и сравнение коллекций строк (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [Как найти разность множеств между двумя списками (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
