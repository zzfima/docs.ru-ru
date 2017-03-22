---
title: "Преобразование типов данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 53d8ad292891a567e13ec8a5396bcc114b379351
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-visual-basic"></a>Преобразование типов данных (Visual Basic)
Методы преобразования изменяют тип входных объектов.  
  
 Операции преобразования в запросах LINQ полезны для различных приложений. Ниже приведены некоторые примеры:  
  
-   <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>Метод может использоваться для скрытия пользовательскую реализацию стандартного оператора запроса типа.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>  
  
-   <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>Метод может использоваться для включения непараметризованным коллекциям для запросов LINQ.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, И <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>методы можно использовать для принудительного немедленного выполнения запроса вместо откладывания до перечисления запроса.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>  
  
## <a name="methods"></a>Методы  
 В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.  
  
 Методы преобразования в этой таблице, имена которых начинаются с «As», изменяют статический тип исходной коллекции, но не перечислить. Методы, имена которых начинаются с «To», перечисляют исходную коллекцию и помещают элементы в коллекции, соответствующий тип.  
  
|Имя метода|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|AsEnumerable|Возвращает входные данные, типизированного как <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601>|Неприменимо.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|Преобразует (универсальный) <xref:System.Collections.IEnumerable>для <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> (универсальный)</xref:System.Collections.IEnumerable>|Неприменимо.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Cast|Приводит элементы коллекции в указанный тип.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|Фильтрует значения в зависимости от их возможности приведения к указанному типу.|Неприменимо.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|Преобразует коллекцию в массив. Этот метод вызывает выполнение запроса.|Неприменимо.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|Помещает элементы в <xref:System.Collections.Generic.Dictionary%602>на основании функции выбора ключа.</xref:System.Collections.Generic.Dictionary%602> Этот метод вызывает выполнение запроса.|Неприменимо.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|Преобразует коллекцию <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> Этот метод вызывает выполнение запроса.|Неприменимо.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|Помещает элементы в <xref:System.Linq.Lookup%602>(словарь "один ко многим") на основании функции выбора ключа.</xref:System.Linq.Lookup%602> Этот метод вызывает выполнение запроса.|Неприменимо.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса  
 В следующем примере кода `From As` предложение для приведения типа к подтипу перед доступом к члену, доступному только для подтипа.  
  
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
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Предложение FROM](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [Практическое руководство: запроса к ArrayList с помощью LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
