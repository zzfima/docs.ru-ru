---
title: "Общие сведения о стандартных операторах запроса (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5b03c85a298b3864a91a7052ca80cf3714ba98fe
ms.lasthandoff: 03/13/2017

---
# <a name="standard-query-operators-overview-c"></a>Общие сведения о стандартных операторах запроса (C#)
*Стандартные операторы запросов* — это методы, формирующие шаблон LINQ. Большинство этих методов применяются к последовательностям, где последовательность — это объект, тип которого реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>. Функциональные возможности стандартных операторов запросов включают фильтрацию, проекцию, статистическую обработку, сортировку и многие другие.  
  
 Существует два набора стандартных операторов запросов LINQ, один из них работает с объектами типа <xref:System.Collections.Generic.IEnumerable%601>, а другой — с объектами типа <xref:System.Linq.IQueryable%601>. Методы, составляющие каждый набор, являются статическими членами классов <xref:System.Linq.Enumerable> и <xref:System.Linq.Queryable> соответственно. Они определяются как *методы расширения* типа, к которому применяются. Это означает, что их можно вызывать, используя либо синтаксис статического метода, либо синтаксис метода экземпляра.  
  
 Кроме того, несколько методов стандартных операторов запросов применяются к типам, отличным от типов на основе <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>. Тип <xref:System.Linq.Enumerable> определяет два таких метода, оба из которых применяются к объектам типа <xref:System.Collections.IEnumerable>. Эти методы, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> и <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, позволяют запрашивать в шаблоне LINQ коллекцию без параметров (не являющуюся универсальной). Для этого создается строго типизированная коллекция объектов. Класс <xref:System.Linq.Queryable> определяет два аналогичных параметра, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> и <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, которые применяются к объектам типа <xref:System.Linq.Queryable>.  
  
 Стандартные операторы запросов имеют различное время выполнения, которое зависит от того, возвращают они одноэлементное значение или последовательность значений. Методы, возвращающие одноэлементное значение (например, <xref:System.Linq.Enumerable.Average%2A> и <xref:System.Linq.Enumerable.Sum%2A>), выполняются незамедлительно. Методы, которые возвращают последовательность, откладывают выполнение запроса и возвращают перечисляемый объект.  
  
 При использовании методов, которые применяются к коллекциям, т. е. методов, которые расширяют <xref:System.Collections.Generic.IEnumerable%601>, возвращаемый перечисляемый объект захватывает переданные в этот метод аргументы. При перечислении этого объекта задействуется логика оператора запросов и возвращаются результаты запросов.  
  
 При этом методы, расширяющие <xref:System.Linq.IQueryable%601>, не реализуют поведение запросов, но формируют дерево выражений, представляющее выполняемый запрос. Обработку запросов выполняет исходный объект <xref:System.Linq.IQueryable%601>.  
  
 Вызовы методов запросов можно объединять в один запрос, в результате чего запросы могут становиться довольно сложными.  
  
 В следующем примере кода показано, как использовать стандартные операторы запросов для получения сведений о последовательности.  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS   
```  
  
## <a name="query-expression-syntax"></a>Синтаксис выражений запросов  
 Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в виде ключевых слов в синтаксисе языка C# и Visual Basic, что позволяет вызывать их как часть *выражения* *запроса*. Дополнительные сведения о стандартных операторах запросов с выделенными ключевыми словами и соответствующим синтаксисом см. в разделе [Синтаксис выражений запросов для стандартных операторов запросов (C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).  
  
## <a name="extending-the-standard-query-operators"></a>Расширение стандартных операторов запросов  
 Набор стандартных операторов запросов можно дополнить, создав специальные методы, соответствующие вашему целевому домену или технологии. Кроме того, можно заменить стандартные операторы запросов на собственные реализации, предоставляющие дополнительные услуги, такие как удаленное вычисление, перевод запросов и оптимизация. Для примера см. <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
## <a name="related-sections"></a>Связанные разделы  
 Следующие ссылки адресуют к разделам, содержащим дополнительные сведения о различных стандартных операторах запросов в зависимости от их функциональности.  
  
 [Сортировка данных (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md)  
  
 [Операции над множествами (C#)](../../../../csharp/programming-guide/concepts/linq/set-operations.md)  
  
 [Фильтрация данных (C#)](../../../../csharp/programming-guide/concepts/linq/filtering-data.md)  
  
 [Операции, использующие квантификаторы (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [Операции проекции (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)  
  
 [Секционирование данных (C#)](../../../../csharp/programming-guide/concepts/linq/partitioning-data.md)  
  
 [Операции соединения (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md)  
  
 [Группирование данных (C#)](../../../../csharp/programming-guide/concepts/linq/grouping-data.md)  
  
 [Операции создания (C#)](../../../../csharp/programming-guide/concepts/linq/generation-operations.md)  
  
 [Операции сравнения (C#)](../../../../csharp/programming-guide/concepts/linq/equality-operations.md)  
  
 [Операции с элементами (C#)](../../../../csharp/programming-guide/concepts/linq/element-operations.md)  
  
 [Преобразование типов данных (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md)  
  
 [Операции объединения (C#)](../../../../csharp/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [Операции агрегирования (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.Enumerable>   
 <xref:System.Linq.Queryable>   
 [Введение в запросы LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)   
 [Синтаксис выражений запроса для стандартных операторов запроса (C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [Классификация стандартных операторов запросов по способу выполнения (C#)](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)   
 [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
