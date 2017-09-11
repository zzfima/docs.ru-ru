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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 94e9627efb183c08bbb67a7e6e82df9132ebdef2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-strings-visual-basic"></a><span data-ttu-id="1f2c2-102">LINQ и строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-102">LINQ and Strings (Visual Basic)</span></span>
<span data-ttu-id="1f2c2-103">LINQ можно использовать для запроса и преобразования строк и коллекций строк.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="1f2c2-104">Может быть особенно полезно для частично структурированных данных в текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="1f2c2-105">Запросы LINQ можно объединять с традиционными строковыми функциями и регулярными выражениями.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="1f2c2-106">Например, можно использовать <xref:System.String.Split%2A>или <xref:System.Text.RegularExpressions.Regex.Split%2A>метод для создания массива строк, которые можно запросить или изменить с помощью LINQ.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="1f2c2-106">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="1f2c2-107">Можно использовать <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>метода в `where` предложения FROM запроса LINQ.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A></span><span class="sxs-lookup"><span data-stu-id="1f2c2-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="1f2c2-108">И LINQ можно использовать для запроса или изменения <xref:System.Text.RegularExpressions.MatchCollection>результаты, возвращенные регулярному выражению.</xref:System.Text.RegularExpressions.MatchCollection></span><span class="sxs-lookup"><span data-stu-id="1f2c2-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="1f2c2-109">Можно также использовать методы, описанные в этом разделе для преобразования частично структурированных текстовых данных в XML.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="1f2c2-110">Дополнительные сведения см. в разделе [Практическое руководство: Создание XML из CSV-файлов](how-to-generate-xml-from-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="1f2c2-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>  
  
 <span data-ttu-id="1f2c2-111">Примеры в этом разделе делятся на две категории:</span><span class="sxs-lookup"><span data-stu-id="1f2c2-111">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="1f2c2-112">Запрос блока текста</span><span class="sxs-lookup"><span data-stu-id="1f2c2-112">Querying a Block of Text</span></span>  
 <span data-ttu-id="1f2c2-113">Запрос, анализировать и изменять блоки текста, разделяя их на запрашиваемые массивы меньших строк с помощью <xref:System.String.Split%2A>метода или <xref:System.Text.RegularExpressions.Regex.Split%2A>метод.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="1f2c2-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="1f2c2-114">Можно разделить исходного текста на слова, предложения, абзацы, страницы или другие критерии и затем выполнить дополнительные разбиения, если они требуются в запросе.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="1f2c2-115">Практическое руководство: количество вхождений слова в строке (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-115">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="1f2c2-116">Показано, как использовать LINQ для простых запросов текста.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-116">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="1f2c2-117">Практическое руководство: запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 <span data-ttu-id="1f2c2-118">Показано разделение текстовых файлов на произвольные и выполнения запросов к каждой части.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="1f2c2-119">Практическое руководство: запрос знаков в строке (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-119">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>](how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="1f2c2-120">Показывает, что строка является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-120">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="1f2c2-121">Практическое руководство: объединение запросов LINQ с регулярными выражениями (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-121">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="1f2c2-122">Показано, как использовать регулярные выражения в запросах LINQ для проверки сложного шаблона на фильтрованных результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="1f2c2-123">Запрос частично структурированных данных в текстовом формате</span><span class="sxs-lookup"><span data-stu-id="1f2c2-123">Querying Semi-Structured Data in Text Format</span></span>  
 <span data-ttu-id="1f2c2-124">Множество различных типов текстовых файлов состоят из ряда строк, часто с одинаковым форматированием, таких как файлы с разделителями запятыми или строки фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="1f2c2-125">После считывания такого текстового файла в память можно использовать LINQ для запросов и/или изменения строк.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="1f2c2-126">LINQ запросы также упрощают задачу объединения данных из нескольких источников.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="1f2c2-127">Практическое руководство: нахождение разности наборов между двумя списками (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-127">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="1f2c2-128">Содержит сведения о поиске всех строк, присутствующих в одном списке, но отсутствуют в другом.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-128">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="1f2c2-129">Практическое руководство: сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="1f2c2-130">Показывает способ сортировки строк текста на основе любого слова или поля.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-130">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="1f2c2-131">Практическое руководство: изменение порядка полей файла с разделителями (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-131">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>](how-to-reorder-the-fields-of-a-delimited-file.md)  
 <span data-ttu-id="1f2c2-132">Описание способов изменения порядка полей в строке CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-132">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="1f2c2-133">Практическое руководство: объединение и сравнение коллекций строк (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-133">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="1f2c2-134">Демонстрация объединения списков строк различными способами.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-134">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="1f2c2-135">Практическое руководство: заполнение коллекций объектов из нескольких источников (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-135">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="1f2c2-136">Показано, как создание коллекций объектов с помощью нескольких текстовых файлов в качестве источников данных.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-136">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="1f2c2-137">Практическое руководство: объединение содержимого из файлов разных форматов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-137">How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="1f2c2-138">Показано, как для объединения строк из двух списков в одну строку с помощью совпадающего ключа.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="1f2c2-139">Практическое руководство: Разделение файла на несколько файлов с помощью групп (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-139">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="1f2c2-140">Показано, как создать новые файлы с помощью одного файла в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-140">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="1f2c2-141">Практическое руководство: вычисление значений столбцов в файле CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-141">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="1f2c2-142">Показано, как для выполнения математических вычислений с текстовыми данными в CSV-файлах.</span><span class="sxs-lookup"><span data-stu-id="1f2c2-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2c2-143">См. также</span><span class="sxs-lookup"><span data-stu-id="1f2c2-143">See Also</span></span>  
 <span data-ttu-id="1f2c2-144">[Интегрированный в язык запрос (LINQ) (Visual Basic)](index.md) </span><span class="sxs-lookup"><span data-stu-id="1f2c2-144">[Language-Integrated Query (LINQ) (Visual Basic)](index.md) </span></span>  
<span data-ttu-id="1f2c2-145"> [Практическое руководство. Создание кода XML из CSV-файлов](how-to-generate-xml-from-csv-files.md)</span><span class="sxs-lookup"><span data-stu-id="1f2c2-145"> [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md)</span></span>

