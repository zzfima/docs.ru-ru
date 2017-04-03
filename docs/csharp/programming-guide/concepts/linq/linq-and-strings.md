---
title: "LINQ и строки (C#) | Документы Майкрософт"
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
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39c181bbf3c865b3c3a7f840b600be3ed6f56a7a
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-strings-c"></a>LINQ и строки (C#)
LINQ можно использовать для запроса и преобразования строк и коллекций строк. При этом лучше всего его потенциал раскрывается при работе с частично структурированными данными в текстовых файлах. Запросы LINQ можно комбинировать с традиционными строковыми функциями и регулярными выражениями. Например, с помощью метода <xref:System.String.Split%2A> или <xref:System.Text.RegularExpressions.Regex.Split%2A> можно создать массив строк, которые можно будет запрашивать или изменять посредством LINQ. Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> можно использовать в предложении `where` запроса LINQ. Кроме того, LINQ позволяет запрашивать или изменять результаты <xref:System.Text.RegularExpressions.MatchCollection>, возвращаемые регулярным выражением.  
  
 Методы, описанные в этом разделе, позволяют преобразовать частично структурированные текстовые данные в XML. Дополнительные сведения см. в разделе [Практическое руководство. Создание кода XML из CSV-файлов](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd).  
  
 Примеры в этом разделе делятся на две категории:  
  
## <a name="querying-a-block-of-text"></a>Запрос блока текста  
 Текстовые блоки можно запрашивать, анализировать и изменять, формируя из них доступный для запросов массив более мелких строк с помощью метода <xref:System.String.Split%2A> или <xref:System.Text.RegularExpressions.Regex.Split%2A>. Исходный текст можно разбить на слова, предложения, абзацы, страницы или другие фрагменты, а затем применить другие способы фрагментации, необходимые для вашего запроса.  
  
 [Практическое руководство. Подсчет вхождений слова в строке (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Показывает, как использовать LINQ для простых запросов текста.  
  
 [Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)  
 Показывает, как разбивать текстовые файлы на произвольные фрагменты и выполнять запросы к каждой части.  
  
 [Практическое руководство. Запрос символов в строке (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-characters-in-a-string-linq.md)  
 Показывает, что строка является запрашиваемым типом.  
  
 [Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)  
 Показывает, как выполнять сопоставление комплексных шаблонов с отфильтрованными результатами запросов, используя регулярные выражения в запросах LINQ.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Запрос частично структурированных данных в текстовом формате  
 Многие типы текстовых файлов состоят из серии строк, которые часто имеют одинаковый формат, например, из файлов с разделителями табуляцией или запятыми либо из строк фиксированной длины. После того как текстовый файл будет считан в память, можно использовать LINQ для запроса и (или) изменения строк. Кроме того, запросы LINQ упрощают задачу объединения данных из различных источников.  
  
 [Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)  
 Показывает, как найти все строки, которые есть в одном списке, но отсутствуют в другом.  
  
 [Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Показывает, как сортировать текстовые строки по какому-либо слову или полю.  
  
 [Практическое руководство. Изменение порядка полей файла с разделителями (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-reorder-the-fields-of-a-delimited-file-linq.md)  
 Показывает, как изменить порядок полей в строке CSV-файла.  
  
 [Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 Показывает различные способы объединения списков строк.  
  
 [Практическое руководство. Заполнение коллекций объектов из нескольких источников (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Показывает, как создавать коллекции объектов, используя в качестве источников данных сразу несколько текстовых файлов.  
  
 [Практическое руководство. Объединение содержимого из файлов разных форматов (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)  
 Показывает, как объединить строки из двух списков в одну строку, используя ключ сопоставления.  
  
 [Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Показывает, как создавать файлы, используя в качестве источника данных одиночный файл.  
  
 [Практическое руководство. Вычисление значений столбцов в текстовом CSV-файле (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Показывает, как выполнять математические расчеты на основе текстовых данных в CSV-файлах.  
  
## <a name="see-also"></a>См. также  
 [LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)   
 [Практическое руководство. Создание кода XML из CSV-файлов](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)
