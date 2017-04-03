---
title: "Сортировка данных (C#) | Документы Майкрософт"
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
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
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
ms.openlocfilehash: 201789725738d06bdda2f8b9765e194c6b4c4115
ms.lasthandoff: 03/13/2017

---
# <a name="sorting-data-c"></a>Сортировка данных (C#)
Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов. Первый критерий сортировки выполняет первичную сортировку элементов. Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.  
  
 На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов.  
  
 ![Операции сортировки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")  
  
 Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OrderBy|Сортировка значений в возрастающем порядке.|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName>|  
|OrderByDescending|Сортировка значений в убывающем порядке.|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName>|  
|ThenBy|Дополнительная сортировка по возрастанию.|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName>|  
|ThenByDescending|Дополнительная сортировка по убыванию.|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName>|  
|Reverse|Изменение порядка элементов в коллекции на обратный.|Неприменимо.|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
  
### <a name="primary-sort-examples"></a>Примеры основной сортировки  
  
#### <a name="primary-ascending-sort"></a>Основная сортировка по возрастанию  
 В следующем примере показано использование предложения `orderby` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a>Основная сортировка по убыванию  
 В следующем примере показано использование предложения `orderby``descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a>Примеры дополнительной сортировки  
  
#### <a name="secondary-ascending-sort"></a>Дополнительная сортировка по возрастанию  
 В следующем примере показано использование предложения `orderby` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве. Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a>Дополнительная сортировка по убыванию  
 В следующем примере показано использование предложения `orderby``descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию. Строки сортируются основным образом по длине и дополнительно — по первой букве строки.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>   
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md)   
 [Практическое руководство. Упорядочение результатов предложения соединения](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
