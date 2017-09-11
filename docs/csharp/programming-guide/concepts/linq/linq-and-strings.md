---
title: "LINQ и строки (C#)"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 49c51595ffff45df503308b9eba55fc67b4da2e8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-strings-c"></a><span data-ttu-id="0def7-102">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-102">LINQ and Strings (C#)</span></span>
<span data-ttu-id="0def7-103">LINQ можно использовать для запроса и преобразования строк и коллекций строк.</span><span class="sxs-lookup"><span data-stu-id="0def7-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="0def7-104">При этом лучше всего его потенциал раскрывается при работе с частично структурированными данными в текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="0def7-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="0def7-105">Запросы LINQ можно комбинировать с традиционными строковыми функциями и регулярными выражениями.</span><span class="sxs-lookup"><span data-stu-id="0def7-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="0def7-106">Например, используя метод <xref:System.String.Split%2A> или <xref:System.Text.RegularExpressions.Regex.Split%2A>, можно создать массив строк, который затем можно запрашивать или изменять с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="0def7-106">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="0def7-107">Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> можно использовать в предложении `where` запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="0def7-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="0def7-108">Также LINQ можно использовать для запроса или изменения результатов <xref:System.Text.RegularExpressions.MatchCollection>, возвращаемых регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="0def7-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="0def7-109">Методы, описанные в этом разделе, позволяют преобразовать частично структурированные текстовые данные в XML.</span><span class="sxs-lookup"><span data-stu-id="0def7-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="0def7-110">Дополнительные сведения см. в разделе [Практическое руководство. Создание кода XML из CSV-файлов](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd).</span><span class="sxs-lookup"><span data-stu-id="0def7-110">For more information, see [How to: Generate XML from CSV Files](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd).</span></span>  
  
 <span data-ttu-id="0def7-111">Примеры в этом разделе делятся на две категории:</span><span class="sxs-lookup"><span data-stu-id="0def7-111">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="0def7-112">Запрос блока текста</span><span class="sxs-lookup"><span data-stu-id="0def7-112">Querying a Block of Text</span></span>  
 <span data-ttu-id="0def7-113">Вы можете запрашивать, анализировать и изменять блоки текста, разбивая их на запрашиваемый массив строк меньшего размера с помощью методов <xref:System.String.Split%2A> или <xref:System.Text.RegularExpressions.Regex.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="0def7-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="0def7-114">Исходный текст можно разбить на слова, предложения, абзацы, страницы или другие фрагменты, а затем применить другие способы фрагментации, необходимые для вашего запроса.</span><span class="sxs-lookup"><span data-stu-id="0def7-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="0def7-115">Практическое руководство. Подсчет вхождений слова в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-115">How to: Count Occurrences of a Word in a String (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="0def7-116">Показывает, как использовать LINQ для простых запросов текста.</span><span class="sxs-lookup"><span data-stu-id="0def7-116">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="0def7-117">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)  
 <span data-ttu-id="0def7-118">Показывает, как разбивать текстовые файлы на произвольные фрагменты и выполнять запросы к каждой части.</span><span class="sxs-lookup"><span data-stu-id="0def7-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="0def7-119">Практическое руководство. Запрос символов в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-119">How to: Query for Characters in a String (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="0def7-120">Показывает, что строка является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="0def7-120">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="0def7-121">Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-121">How to: Combine LINQ Queries with Regular Expressions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="0def7-122">Показывает, как выполнять сопоставление комплексных шаблонов с отфильтрованными результатами запросов, используя регулярные выражения в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="0def7-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="0def7-123">Запрос частично структурированных данных в текстовом формате</span><span class="sxs-lookup"><span data-stu-id="0def7-123">Querying Semi-Structured Data in Text Format</span></span>  
 <span data-ttu-id="0def7-124">Многие типы текстовых файлов состоят из серии строк, которые часто имеют одинаковый формат, например, из файлов с разделителями табуляцией или запятыми либо из строк фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="0def7-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="0def7-125">После того как текстовый файл будет считан в память, можно использовать LINQ для запроса и (или) изменения строк.</span><span class="sxs-lookup"><span data-stu-id="0def7-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="0def7-126">Кроме того, запросы LINQ упрощают задачу объединения данных из различных источников.</span><span class="sxs-lookup"><span data-stu-id="0def7-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="0def7-127">Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-127">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="0def7-128">Показывает, как найти все строки, которые есть в одном списке, но отсутствуют в другом.</span><span class="sxs-lookup"><span data-stu-id="0def7-128">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="0def7-129">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="0def7-130">Показывает, как сортировать текстовые строки по какому-либо слову или полю.</span><span class="sxs-lookup"><span data-stu-id="0def7-130">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="0def7-131">Практическое руководство. Изменение порядка полей файла с разделителями (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-131">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-reorder-the-fields-of-a-delimited-file-linq.md)  
 <span data-ttu-id="0def7-132">Показывает, как изменить порядок полей в строке CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="0def7-132">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="0def7-133">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-133">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="0def7-134">Показывает различные способы объединения списков строк.</span><span class="sxs-lookup"><span data-stu-id="0def7-134">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="0def7-135">Практическое руководство. Заполнение коллекций объектов из нескольких источников (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-135">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="0def7-136">Показывает, как создавать коллекции объектов, используя в качестве источников данных сразу несколько текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="0def7-136">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="0def7-137">Практическое руководство. Объединение содержимого из файлов разных форматов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-137">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="0def7-138">Показывает, как объединить строки из двух списков в одну строку, используя ключ сопоставления.</span><span class="sxs-lookup"><span data-stu-id="0def7-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="0def7-139">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-139">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="0def7-140">Показывает, как создавать файлы, используя в качестве источника данных одиночный файл.</span><span class="sxs-lookup"><span data-stu-id="0def7-140">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="0def7-141">Практическое руководство. Вычисление значений столбцов в текстовом CSV-файле (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0def7-141">How to: Compute Column Values in a CSV Text File (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="0def7-142">Показывает, как выполнять математические расчеты на основе текстовых данных в CSV-файлах.</span><span class="sxs-lookup"><span data-stu-id="0def7-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0def7-143">См. также</span><span class="sxs-lookup"><span data-stu-id="0def7-143">See Also</span></span>  
 <span data-ttu-id="0def7-144">[LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="0def7-144">[Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md) </span></span>  
 [<span data-ttu-id="0def7-145">Практическое руководство. Создание кода XML из CSV-файлов</span><span class="sxs-lookup"><span data-stu-id="0def7-145">How to: Generate XML from CSV Files</span></span>](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)

