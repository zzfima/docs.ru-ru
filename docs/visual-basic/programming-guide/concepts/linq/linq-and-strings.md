---
title: LINQ и строки
ms.date: 07/20/2015
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
ms.openlocfilehash: 73ce4bf5586f1f9ff4995ea6f425b90744b7e333
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353287"
---
# <a name="linq-and-strings-visual-basic"></a>LINQ and Strings (Visual Basic)
LINQ можно использовать для запроса и преобразования строк и коллекций строк. При этом лучше всего его потенциал раскрывается при работе с частично структурированными данными в текстовых файлах. Запросы LINQ можно комбинировать с традиционными строковыми функциями и регулярными выражениями. Например, используя метод <xref:System.String.Split%2A> или <xref:System.Text.RegularExpressions.Regex.Split%2A>, можно создать массив строк, который затем можно запрашивать или изменять с помощью LINQ. Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> можно использовать в предложении `where` запроса LINQ. Также LINQ можно использовать для запроса или изменения результатов <xref:System.Text.RegularExpressions.MatchCollection>, возвращаемых регулярным выражением.  
  
 Методы, описанные в этом разделе, позволяют преобразовать частично структурированные текстовые данные в XML. Дополнительные сведения см. в разделе [Практическое руководство. Создание кода XML из CSV-файлов](how-to-generate-xml-from-csv-files.md).  
  
 Примеры в этом разделе делятся на две категории:  
  
## <a name="querying-a-block-of-text"></a>Запрос блока текста  
 Вы можете запрашивать, анализировать и изменять блоки текста, разбивая их на запрашиваемый массив строк меньшего размера с помощью методов <xref:System.String.Split%2A> или <xref:System.Text.RegularExpressions.Regex.Split%2A>. Исходный текст можно разбить на слова, предложения, абзацы, страницы или другие фрагменты, а затем применить другие способы фрагментации, необходимые для вашего запроса.  
  
 [How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Показывает, как использовать LINQ для простых запросов текста.  
  
 [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Показывает, как разбивать текстовые файлы на произвольные фрагменты и выполнять запросы к каждой части.  
  
 [How to: Query for Characters in a String (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Показывает, что строка является запрашиваемым типом.  
  
 [How to combine LINQ queries with regular expressions (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Показывает, как выполнять сопоставление комплексных шаблонов с отфильтрованными результатами запросов, используя регулярные выражения в запросах LINQ.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Запрос частично структурированных данных в текстовом формате  
 Многие типы текстовых файлов состоят из серии строк, которые часто имеют одинаковый формат, например, из файлов с разделителями табуляцией или запятыми либо из строк фиксированной длины. После того как текстовый файл будет считан в память, можно использовать LINQ для запроса и (или) изменения строк. Кроме того, запросы LINQ упрощают задачу объединения данных из различных источников.  
  
 [How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Показывает, как найти все строки, которые есть в одном списке, но отсутствуют в другом.  
  
 [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Показывает, как сортировать текстовые строки по какому-либо слову или полю.  
  
 [How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Показывает, как изменить порядок полей в строке CSV-файла.  
  
 [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Показывает различные способы объединения списков строк.  
  
 [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Показывает, как создавать коллекции объектов, используя в качестве источников данных сразу несколько текстовых файлов.  
  
 [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Показывает, как объединить строки из двух списков в одну строку, используя ключ сопоставления.  
  
 [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Показывает, как создавать файлы, используя в качестве источника данных одиночный файл.  
  
 [How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Показывает, как выполнять математические расчеты на основе текстовых данных в CSV-файлах.  
  
## <a name="see-also"></a>См. также

- [Синтаксис LINQ (Visual Basic)](index.md)
- [Практическое руководство. Создание кода XML из CSV-файлов](how-to-generate-xml-from-csv-files.md)
