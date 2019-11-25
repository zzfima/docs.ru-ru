---
title: Операции проецирования
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: d7efb46ccfe3208ae6c58043a64c236171d0c147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346620"
---
# <a name="projection-operations-visual-basic"></a>Projection Operations (Visual Basic)

Проекцией называют операцию преобразования объекта в новую форму, которая часто состоит только из тех его свойств, которые будут использоваться впоследствии. С помощью проекции можно создать новый тип, построенный из каждого объекта. Вы можете проецировать свойство и выполнять над ним математические функции. Также можно проецировать исходный объект, не изменяя его.

Методы стандартных операторов запросов, которые выполняют проецирование, перечислены в следующем разделе.

## <a name="methods"></a>Методы

|Имя метода|Описание|Visual Basic Query Expression Syntax|Дополнительные сведения|
|-----------------|-----------------|------------------------------------------|----------------------|
|Выбрать|Проецирует значения, основанные на функции преобразования.|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|
|SelectMany|Проецирует последовательности значений, основанных на функции преобразования, а затем выравнивает их в одну последовательность.|Использование нескольких предложений `From`|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов

### <a name="select"></a>Выбрать

В приведенном ниже примере предложение `Select` используется для проецирования первой буквы из каждой строки в списке строк.

```vb
Dim words = New List(Of String) From {"an", "apple", "a", "day"}

Dim query = From word In words
            Select word.Substring(0, 1)

Dim sb As New System.Text.StringBuilder()
For Each letter As String In query
    sb.AppendLine(letter)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' a
' a
' a
' d
```

### <a name="selectmany"></a>SelectMany

The following example uses multiple `From` clauses to project each word from each string in a list of strings.

```vb
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}

Dim query = From phrase In phrases
            From word In phrase.Split(" "c)
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' an
' apple
' a
' day
' the
' quick
' brown
' fox
```

## <a name="select-versus-selectmany"></a>Select или SelectMany

Задача обоих методов `Select()` и `SelectMany()` заключается в создании результирующего значения (или значений) из исходных значений. `Select()` создает один результат для каждого исходного значения. Таким образом, общий результат является коллекцией, имеющей то же количество элементов, что и исходная коллекция. `SelectMany()`, напротив, создает общий результат, содержащий соединенные подколлекции из каждого исходного значения. Функция преобразования, которая передается в качестве аргумента методу `SelectMany()`, должна возвращать перечисляемую последовательность значений для каждого исходного значения. Эти перечисляемые последовательности затем объединяются `SelectMany()` для создания одной большой последовательности.

На двух рисунках, приведенных ниже, показаны принципиальные различия между работой этих двух методов. В обоих случаях предполагается, что функция выбора (преобразования) выбирает массив цветов из каждого исходного значения.

На этом рисунке представлено, как `Select()` возвращает коллекцию, которая имеет то же количество элементов, что и исходная коллекция.

![График, отображающий действие Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)

На этом рисунке показано, как `SelectMany()` объединяет промежуточные последовательности массивов в один конечный результат, содержащий все значения из промежуточных массивов.

![График, отображающий действие SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )

### <a name="code-example"></a>Пример кода

В приведенном ниже примере сравнивается действие `Select()` и `SelectMany()`. Код создает "букет" из цветов путем получения первых двух элементов из каждого списка названий цветов в исходной коллекции. В этом примере отдельное значение, используемое функцией преобразования <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>, представляет собой коллекцию значений. Этот требует дополнительного цикла `For Each` для перечисления каждой строки в каждой подпоследовательности.

```vb
Class Bouquet
    Public Flowers As List(Of String)
End Class

Sub SelectVsSelectMany()
    Dim bouquets = New List(Of Bouquet) From {
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}

    Dim output As New System.Text.StringBuilder

    ' Select()
    Dim query1 = bouquets.Select(Function(b) b.Flowers)

    output.AppendLine("Using Select():")
    For Each flowerList In query1
        For Each str As String In flowerList
            output.AppendLine(str)
        Next
    Next

    ' SelectMany()
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)

    output.AppendLine(vbCrLf & "Using SelectMany():")
    For Each str As String In query2
        output.AppendLine(str)
    Next

    ' Display the output
    MsgBox(output.ToString())

    ' This code produces the following output:
    '
    ' Using Select():
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

    ' Using SelectMany()
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

End Sub
```

## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md)
- [How to: Combine Data with Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md) (Практическое руководство. Объединение данных с помощью соединений)
- [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)
- [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
