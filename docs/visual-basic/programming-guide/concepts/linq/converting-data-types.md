---
title: Преобразование типов данных
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 25d21954f0bb7555f1f5666f83fb37f4f73e2a60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354256"
---
# <a name="converting-data-types-visual-basic"></a>Преобразование типов данных (Visual Basic)

Методы преобразования изменяют тип входных объектов.

 Операции преобразования в запросах LINQ удобны в различных ситуациях. Рассмотрим несколько примеров.

- Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> можно использовать, чтобы скрыть настраиваемую реализацию типа стандартного оператора запроса.

- Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> позволяет использовать непараметризованные коллекции для запросов LINQ.

- Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> можно использовать для принудительного немедленного выполнения запроса, не дожидаясь, пока этот запрос будет перечислен.

## <a name="methods"></a>Методы

В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.

Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление. Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.

|Имя метода|Описание|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|
|-----------------|-----------------|------------------------------------------|----------------------|
|AsEnumerable|Возвращает входное значение, типизированное как <xref:System.Collections.Generic.IEnumerable%601>.|Неприменимо.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|AsQueryable|Преобразует <xref:System.Collections.IEnumerable> (универсальный шаблон) в <xref:System.Linq.IQueryable> (универсальный шаблон).|Неприменимо.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|Cast|Приводит элементы коллекции к указанному типу.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|OfType|Фильтрует значения в зависимости от возможности их приведения к указанному типу.|Неприменимо.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|ToArray|Преобразует коллекцию в массив. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|ToDictionary|Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|ToList|Преобразует коллекцию в <xref:System.Collections.Generic.List%601>. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|ToLookup|Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса

В следующем примере кода используется предложение `From As` для приведения типа к подтипу перед доступом к элементу, доступному только для подтипа.

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Как выполнить запрос к ArrayList с помощью LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
