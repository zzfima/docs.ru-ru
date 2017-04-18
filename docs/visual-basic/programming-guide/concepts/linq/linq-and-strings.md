---
title: "LINQ и строки (Visual Basic) | Документы Microsoft"
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
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a79d1427331070da9c545fdd3175115fe187e879
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-strings-visual-basic"></a>LINQ и строки (Visual Basic)
LINQ можно использовать для запроса и преобразования строк и коллекций строк. Может быть особенно полезно для частично структурированных данных в текстовых файлах. Запросы LINQ можно объединять с традиционными строковыми функциями и регулярными выражениями. Например, можно использовать <xref:System.String.Split%2A>или <xref:System.Text.RegularExpressions.Regex.Split%2A>метод для создания массива строк, которые можно запросить или изменить с помощью LINQ.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> Можно использовать <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>метода в `where` предложения FROM запроса LINQ.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A> И LINQ можно использовать для запроса или изменения <xref:System.Text.RegularExpressions.MatchCollection>результаты, возвращенные регулярному выражению.</xref:System.Text.RegularExpressions.MatchCollection>  
  
 Можно также использовать методы, описанные в этом разделе для преобразования частично структурированных текстовых данных в XML. Дополнительные сведения см. в разделе [Практическое руководство: Создание XML из CSV-файлов](how-to-generate-xml-from-csv-files.md).  
  
 Примеры в этом разделе делятся на две категории:  
  
## <a name="querying-a-block-of-text"></a>Запрос блока текста  
 Запрос, анализировать и изменять блоки текста, разделяя их на запрашиваемые массивы меньших строк с помощью <xref:System.String.Split%2A>метода или <xref:System.Text.RegularExpressions.Regex.Split%2A>метод.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> Можно разделить исходного текста на слова, предложения, абзацы, страницы или другие критерии и затем выполнить дополнительные разбиения, если они требуются в запросе.  
  
 [Практическое руководство: количество вхождений слова в строке (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Показано, как использовать LINQ для простых запросов текста.  
  
 [Практическое руководство: запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic)](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Показано разделение текстовых файлов на произвольные и выполнения запросов к каждой части.  
  
 [Практическое руководство: запрос знаков в строке (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Показывает, что строка является запрашиваемым типом.  
  
 [Практическое руководство: объединение запросов LINQ с регулярными выражениями (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Показано, как использовать регулярные выражения в запросах LINQ для проверки сложного шаблона на фильтрованных результатах запроса.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Запрос частично структурированных данных в текстовом формате  
 Множество различных типов текстовых файлов состоят из ряда строк, часто с одинаковым форматированием, таких как файлы с разделителями запятыми или строки фиксированной длины. После считывания такого текстового файла в память можно использовать LINQ для запросов и/или изменения строк. LINQ запросы также упрощают задачу объединения данных из нескольких источников.  
  
 [Практическое руководство: нахождение разности наборов между двумя списками (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Содержит сведения о поиске всех строк, присутствующих в одном списке, но отсутствуют в другом.  
  
 [Практическое руководство: сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Показывает способ сортировки строк текста на основе любого слова или поля.  
  
 [Практическое руководство: изменение порядка полей файла с разделителями (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Описание способов изменения порядка полей в строке CSV-файла.  
  
 [Практическое руководство: объединение и сравнение коллекций строк (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Демонстрация объединения списков строк различными способами.  
  
 [Практическое руководство: заполнение коллекций объектов из нескольких источников (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Показано, как создание коллекций объектов с помощью нескольких текстовых файлов в качестве источников данных.  
  
 [Практическое руководство: объединение содержимого из файлов разных форматов (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Показано, как для объединения строк из двух списков в одну строку с помощью совпадающего ключа.  
  
 [Практическое руководство: Разделение файла на несколько файлов с помощью групп (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Показано, как создать новые файлы с помощью одного файла в качестве источника данных.  
  
 [Практическое руководство: вычисление значений столбцов в файле CSV (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Показано, как для выполнения математических вычислений с текстовыми данными в CSV-файлах.  
  
## <a name="see-also"></a>См. также  
 [Интегрированный в язык запрос (LINQ) (Visual Basic)](index.md)   
 [Практическое руководство. Создание кода XML из CSV-файлов](how-to-generate-xml-from-csv-files.md)

