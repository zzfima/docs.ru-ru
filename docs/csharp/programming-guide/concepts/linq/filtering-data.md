---
title: "Фильтрация данных (C#)"
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
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: defa6716f677c44da5dd27cb64b3b1d140a65272
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="filtering-data-c"></a>Фильтрация данных (C#)
Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию. Это также называется выборкой.  
  
 На следующем рисунке показаны результаты операции фильтрации последовательности символов. Предикат для операции фильтрации указывает, что символ должен быть "A".  
  
 ![Операция фильтрации LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OfType|Выбирает значения в зависимости от возможности приведения их к указанному типу.|Неприменимо.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|Where|Выбирает значения, основанные на функции предиката.|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса  
 В следующем примере для выбора из массива строк, имеющих определенную длину, используется предложение `where`.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>   
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Предложение where](../../../../csharp/language-reference/keywords/where-clause.md)   
 [Практическое руководство. Динамическое определение фильтров предикатов во время выполнения](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)   
 [Практическое руководство. Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)   
 [Практическое руководство. Запрос файлов с указанными атрибутами или именем (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)   
 [Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

