---
title: LINQ и строки (C#)
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: fb1714c54331ead80cd28435cf3ed1c4c54a704e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140896"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="6c3df-102">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-102">LINQ and strings (C#)</span></span>

<span data-ttu-id="6c3df-103">LINQ можно использовать для запроса и преобразования строк и коллекций строк.</span><span class="sxs-lookup"><span data-stu-id="6c3df-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="6c3df-104">При этом лучше всего его потенциал раскрывается при работе с частично структурированными данными в текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="6c3df-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="6c3df-105">Запросы LINQ можно комбинировать с традиционными строковыми функциями и регулярными выражениями.</span><span class="sxs-lookup"><span data-stu-id="6c3df-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="6c3df-106">Например, используя метод <xref:System.String.Split%2A?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>, можно создать массив строк, который затем можно запрашивать или изменять с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="6c3df-106">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="6c3df-107">Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> можно использовать в предложении `where` запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="6c3df-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="6c3df-108">Также LINQ можно использовать для запроса или изменения результатов <xref:System.Text.RegularExpressions.MatchCollection>, возвращаемых регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="6c3df-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="6c3df-109">Методы, описанные в этом разделе, позволяют преобразовать частично структурированные текстовые данные в XML.</span><span class="sxs-lookup"><span data-stu-id="6c3df-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="6c3df-110">Дополнительные сведения см. в разделе [Практическое руководство. Создание XML из CSV-файлов (C#)](how-to-generate-xml-from-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="6c3df-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="6c3df-111">Примеры в этом разделе делятся на две категории:</span><span class="sxs-lookup"><span data-stu-id="6c3df-111">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="6c3df-112">Запрос блока текста</span><span class="sxs-lookup"><span data-stu-id="6c3df-112">Querying a block of text</span></span>

<span data-ttu-id="6c3df-113">Вы можете запрашивать, анализировать и изменять блоки текста, разбивая их на запрашиваемый массив строк меньшего размера с помощью методов <xref:System.String.Split%2A?displayProperty=nameWithType> или <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c3df-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6c3df-114">Исходный текст можно разбить на слова, предложения, абзацы, страницы или другие фрагменты, а затем применить другие способы фрагментации, необходимые для вашего запроса.</span><span class="sxs-lookup"><span data-stu-id="6c3df-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="6c3df-115">Практическое руководство. Подсчет вхождений слова в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-115">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="6c3df-116">Показывает, как использовать LINQ для простых запросов текста.</span><span class="sxs-lookup"><span data-stu-id="6c3df-116">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="6c3df-117">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="6c3df-118">Показывает, как разбивать текстовые файлы на произвольные фрагменты и выполнять запросы к каждой части.</span><span class="sxs-lookup"><span data-stu-id="6c3df-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="6c3df-119">Практическое руководство. Запрос символов в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-119">How to: Query for Characters in a String (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="6c3df-120">Показывает, что строка является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="6c3df-120">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="6c3df-121">Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-121">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="6c3df-122">Показывает, как выполнять сопоставление комплексных шаблонов с отфильтрованными результатами запросов, используя регулярные выражения в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="6c3df-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="6c3df-123">Запрос частично структурированных данных в текстовом формате</span><span class="sxs-lookup"><span data-stu-id="6c3df-123">Querying semi-structured data in text format</span></span>

<span data-ttu-id="6c3df-124">Многие типы текстовых файлов состоят из серии строк, которые часто имеют одинаковый формат, например, из файлов с разделителями табуляцией или запятыми либо из строк фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="6c3df-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="6c3df-125">После того как текстовый файл будет считан в память, можно использовать LINQ для запроса и (или) изменения строк.</span><span class="sxs-lookup"><span data-stu-id="6c3df-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="6c3df-126">Кроме того, запросы LINQ упрощают задачу объединения данных из различных источников.</span><span class="sxs-lookup"><span data-stu-id="6c3df-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="6c3df-127">Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-127">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="6c3df-128">Показывает, как найти все строки, которые есть в одном списке, но отсутствуют в другом.</span><span class="sxs-lookup"><span data-stu-id="6c3df-128">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="6c3df-129">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="6c3df-130">Показывает, как сортировать текстовые строки по какому-либо слову или полю.</span><span class="sxs-lookup"><span data-stu-id="6c3df-130">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="6c3df-131">Практическое руководство. Изменение порядка полей файла с разделителями (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-131">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="6c3df-132">Показывает, как изменить порядок полей в строке CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="6c3df-132">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="6c3df-133">Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-133">How to: combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="6c3df-134">Показывает различные способы объединения списков строк.</span><span class="sxs-lookup"><span data-stu-id="6c3df-134">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="6c3df-135">Практическое руководство. Заполнение коллекций объектов из нескольких источников (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-135">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="6c3df-136">Показывает, как создавать коллекции объектов, используя в качестве источников данных сразу несколько текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="6c3df-136">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="6c3df-137">Практическое руководство. Объединение содержимого из файлов разных форматов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-137">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="6c3df-138">Показывает, как объединить строки из двух списков в одну строку, используя ключ сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6c3df-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="6c3df-139">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-139">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="6c3df-140">Показывает, как создавать файлы, используя в качестве источника данных одиночный файл.</span><span class="sxs-lookup"><span data-stu-id="6c3df-140">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="6c3df-141">Практическое руководство. Вычисление значений столбцов в текстовом CSV-файле (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-141">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="6c3df-142">Показывает, как выполнять математические расчеты на основе текстовых данных в CSV-файлах.</span><span class="sxs-lookup"><span data-stu-id="6c3df-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c3df-143">См. также</span><span class="sxs-lookup"><span data-stu-id="6c3df-143">See also</span></span>

- [<span data-ttu-id="6c3df-144">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="6c3df-144">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="6c3df-145">Практическое руководство. Создание XML из CSV-файлов</span><span class="sxs-lookup"><span data-stu-id="6c3df-145">How to: Generate XML from CSV Files</span></span>](how-to-generate-xml-from-csv-files.md)
