---
title: "Общие сведения о стандартных операторах (Visual Basic) | Документы Microsoft"
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
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: eb28988ef49e0583fb7e9197c4e13c84665074ac
ms.lasthandoff: 03/13/2017

---
# <a name="standard-query-operators-overview-visual-basic"></a>Общие сведения о стандартных операторах (Visual Basic)
*Стандартные операторы запросов* методы, образующие шаблон LINQ. Большинство этих методов работают с последовательностями, где последовательность — это объект, тип которого реализует <xref:System.Collections.Generic.IEnumerable%601>интерфейс или <xref:System.Linq.IQueryable%601>интерфейса.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> Стандартные операторы запросов предоставляют возможности запроса, включая фильтрацию, проекцию, статистическую, сортировка и многое другое.  
  
 Существует два набора стандартных операторов запросов LINQ, один, работающий с объектами типа <xref:System.Collections.Generic.IEnumerable%601>, а другой, работающий с объектами типа <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> Методы, которые составляют каждый набор являются статическими членами <xref:System.Linq.Enumerable>и <xref:System.Linq.Queryable>классы соответственно.</xref:System.Linq.Queryable> </xref:System.Linq.Enumerable> Они определяются как *методы расширения* типа, они работают. Это означает, что их можно вызывать с помощью синтаксиса статического метода или синтаксис метода экземпляра.  
  
 Кроме того несколько методов стандартных операторов запросов работают с типами, отличными от тех, на основе <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.Enumerable>Тип определяет два метода, оба работают с объектами типа <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable> Эти методы <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29>и <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, позволяют включить коллекцию без параметров или универсальным, должны запрашиваться в шаблоне LINQ.</xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> </xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> Это делается путем создания строго типизированной коллекции объектов. <xref:System.Linq.Queryable>Класс определяет два аналогичных методов <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29>и <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, которые работают с объектами типа <xref:System.Linq.Queryable>.</xref:System.Linq.Queryable> </xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable>  
  
 Стандартные операторы запросов отличаются по времени их выполнения, в зависимости от того, возвращают они одноэлементное значение или последовательность значений. Методы, возвращающие одноэлементное значение (например, <xref:System.Linq.Enumerable.Average%2A>и <xref:System.Linq.Enumerable.Sum%2A>) выполняются немедленно.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Average%2A> Методы, которые возвращают последовательности отложить выполнение запроса и возвращает перечислимый объект.  
  
 При использовании методов, которые работают с коллекциями в памяти, то есть те методы, которые расширяют <xref:System.Collections.Generic.IEnumerable%601>, возвращаемый перечисляемый объект захватывает аргументы, переданные в метод.</xref:System.Collections.Generic.IEnumerable%601> При перечислении объекта используется логика оператора запроса применяется и возвращаются результаты запроса.  
  
 Напротив, методы, расширяющие <xref:System.Linq.IQueryable%601>не реализуют поведение любого запроса, а строят дерево выражения, которое представляет выполняемый запрос.</xref:System.Linq.IQueryable%601> Обработка запросов проходит по источнику <xref:System.Linq.IQueryable%601>объекта.</xref:System.Linq.IQueryable%601>  
  
 Вызовы методов запроса могут быть объединены в один запрос, который позволяет выполнять запросы к усложнению.  
  
 В следующем примере кода показано, как стандартные операторы запроса можно использовать для получения сведений о последовательности.  
  
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
 Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в C# и Visual Basic синтаксис ключевого слова языка, что позволяет им вызывается как часть *запроса* *выражение*. Дополнительные сведения о стандартных операторах запросов, обладающих выделенными ключевыми словами и их синтаксисе см. в разделе [синтаксис выражений запроса для стандартных операторов запросов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).  
  
## <a name="extending-the-standard-query-operators"></a>Расширение стандартных операторов запросов  
 Набор стандартных операторов запросов можно дополнить путем создания доменного методы, которые подходят для целевой предметной области или технологии. Можно также заменить стандартные операторы запросов собственными реализациями, предоставляющими дополнительную функциональность, например удаленное выполнение, преобразование запроса и оптимизации. В разделе <xref:System.Linq.Enumerable.AsEnumerable%2A>пример.</xref:System.Linq.Enumerable.AsEnumerable%2A>  
  
## <a name="related-sections"></a>Связанные разделы  
 Следующие ссылки, чтобы занять на разделы, содержащие дополнительные сведения о различных стандартных операторов запросов на основе функциональности.  
  
 [Сортировка данных](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
  
 [Набор операций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)  
  
 [Фильтрация данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)  
  
 [Операции, использующие кванторы (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [Операции проецирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
  
 [Секционирование данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)  
  
 [Объединение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)  
  
 [Группирование данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)  
  
 [Операции создания (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)  
  
 [Операции равенства (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)  
  
 [Операции с элементами (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)  
  
 [Преобразование типов данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)  
  
 [Операции объединения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [Операции статистической обработки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 <xref:System.Linq.Queryable></xref:System.Linq.Queryable>   
 [Введение в LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)   
 [Синтаксис выражений запроса для стандартных операторов запросов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [Классификация стандартных операторов запросов по способу выполнения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)   
 [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
