---
title: Общие сведения о стандартных операторах запроса
ms.date: 07/20/2015
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
ms.openlocfilehash: 9660e1d92db87e1ae906b3fd6616a51c8b8715fa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349301"
---
# <a name="standard-query-operators-overview-visual-basic"></a>Standard Query Operators Overview (Visual Basic)

*Стандартные операторы запросов* — это методы, формирующие шаблон LINQ. Большинство этих методов работают с последовательностями. В данном контексте последовательность — это объект, тип которого реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>. Функциональные возможности стандартных операторов запросов включают фильтрацию, проекцию, статистическую обработку, сортировку и многие другие.

Существует два набора стандартных операторов запросов LINQ, один из них работает с объектами типа <xref:System.Collections.Generic.IEnumerable%601>, а другой — с объектами типа <xref:System.Linq.IQueryable%601>. Методы, входящие в каждый из наборов, являются статическими членами классов <xref:System.Linq.Enumerable> и <xref:System.Linq.Queryable> соответственно. Они определяются как *методы расширения* типа, к которому применяются. Это означает, что их можно вызывать, используя либо синтаксис статического метода, либо синтаксис метода экземпляра.

Кроме того, несколько стандартных методов операторов запроса работают с типами, отличными от основанных на <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>. Тип <xref:System.Linq.Enumerable> определяет два таких метода, которые работают с объектами типа <xref:System.Collections.IEnumerable>. Эти методы (<xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> и <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>) позволяют выполнять запрос к непараметризованным или не являющимся универсальными коллекциям с использованием шаблона LINQ. Для этого создается строго типизированная коллекция объектов. Класс <xref:System.Linq.Queryable> определяет два схожих метода (<xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> и <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>), которые работают с объектами типа <xref:System.Linq.Queryable>.

Стандартные операторы запросов имеют различное время выполнения, которое зависит от того, возвращают они одноэлементное значение или последовательность значений. Методы, возвращающие одноэлементное значение (например, <xref:System.Linq.Enumerable.Average%2A> и <xref:System.Linq.Enumerable.Sum%2A>), выполняются одновременно. Методы, которые возвращают последовательность, откладывают выполнение запроса и возвращают перечисляемый объект.

При использовании методов, которые применяются к коллекциям, т. е. методов, которые расширяют <xref:System.Collections.Generic.IEnumerable%601>, возвращаемый перечисляемый объект захватывает переданные в этот метод аргументы. При перечислении этого объекта задействуется логика оператора запросов и возвращаются результаты запросов.

При этом методы, расширяющие <xref:System.Linq.IQueryable%601>, не реализуют поведение запросов, но формируют дерево выражения, представляющее выполняемый запрос. Запрос обрабатывается объектом <xref:System.Linq.IQueryable%601> источника.

Вызовы методов запросов можно объединять в один запрос, в результате чего запросы могут становиться довольно сложными.

В следующем примере кода показано, как использовать стандартные операторы запросов для получения сведений о последовательности.

```vb
Dim sentence = "the quick brown fox jumps over the lazy dog"
' Split the string into individual words to create a collection.
Dim words = sentence.Split(" "c)

Dim query = From word In words
            Group word.ToUpper() By word.Length Into gr = Group
            Order By Length _
            Select Length, GroupedWords = gr

Dim output As New System.Text.StringBuilder
For Each obj In query
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))
    For Each word As String In obj.GroupedWords
        output.AppendLine(word)
    Next
Next

'Display the output
MsgBox(output.ToString())

' This code example produces the following output:
'
' Words of length 3:
' THE
' FOX
' THE
' DOG
' Words of length 4:
' OVER
' LAZY
' Words of length 5:
' QUICK
' BROWN
' JUMPS
```

## <a name="query-expression-syntax"></a>Синтаксис выражений запросов

Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в виде ключевых слов в синтаксисе языка C# и Visual Basic, что позволяет вызывать их как часть *выражения* *запроса*. For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).

## <a name="extending-the-standard-query-operators"></a>Расширение стандартных операторов запросов

Набор стандартных операторов запросов можно дополнить, создав специальные методы, соответствующие вашему целевому домену или технологии. Кроме того, можно заменить стандартные операторы запросов на собственные реализации, предоставляющие дополнительные услуги, такие как удаленное вычисление, перевод запросов и оптимизация. Пример см. в разделе <xref:System.Linq.Enumerable.AsEnumerable%2A>.

## <a name="related-sections"></a>Связанные разделы

Следующие ссылки адресуют к разделам, содержащим дополнительные сведения о различных стандартных операторах запросов в зависимости от их функциональности.

- [Сортировка данных](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)

- [Set Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)

- [Filtering Data (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)

- [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)

- [Projection Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)

- [Partitioning Data (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)

- [Join Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)

- [Grouping Data (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)

- [Generation Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)

- [Equality Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)

- [Element Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)

- [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)

- [Concatenation Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)

- [Aggregation Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)

## <a name="see-also"></a>См. также

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Знакомство с LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [Classification of Standard Query Operators by Manner of Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
- [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
