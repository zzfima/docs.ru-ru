---
title: "LINQ и каталоги файлов (Visual Basic) | Документы Microsoft"
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
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9e814c9e9f8519522f288657d6940b07a0b3094
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="5d42e-102">LINQ и каталоги файлов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-102">LINQ and File Directories (Visual Basic)</span></span>
<span data-ttu-id="5d42e-103">Многие операции файловой системы, по существу запросов и, следовательно, хорошо подходит для подход LINQ.</span><span class="sxs-lookup"><span data-stu-id="5d42e-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="5d42e-104">Обратите внимание, что запросы в этом разделе являются безопасными.</span><span class="sxs-lookup"><span data-stu-id="5d42e-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="5d42e-105">Они не используются для изменения содержимого исходных файлов или папок.</span><span class="sxs-lookup"><span data-stu-id="5d42e-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="5d42e-106">Эта процедура выполняется правило, запросы не должны вызывать никаких побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="5d42e-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="5d42e-107">Как правило любой код (включая запросы, выполняющие создания, обновления и удаления операторов), изменяющий исходные данные должны храниться отдельно от кода, который просто запрашивает данные.</span><span class="sxs-lookup"><span data-stu-id="5d42e-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="5d42e-108">В этом разделе рассматриваются следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="5d42e-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="5d42e-109">Практическое руководство: запрос файлов с указанными атрибутами или именем (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-109">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="5d42e-110">Описание способов поиска файлов путем проверки одного или нескольких свойств его <xref:System.IO.FileInfo>объекта.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5d42e-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="5d42e-111">Практическое руководство: группировка файлов по расширению (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-111">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="5d42e-112">Описание способов возврата групп <xref:System.IO.FileInfo>объекта в зависимости от расширения имени файла.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5d42e-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="5d42e-113">Практическое руководство: запрос общее количество байтов в наборе папок (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="5d42e-114">Показано, как вернуть общее число байтов во всех файлах в указанном дереве каталогов.</span><span class="sxs-lookup"><span data-stu-id="5d42e-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="5d42e-115">[Практическое руководство: сравнение содержимого двух папок (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span><span class="sxs-lookup"><span data-stu-id="5d42e-115">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="5d42e-116">Показано, как вернуть все файлы, присутствующие в двух указанных папках, а также все файлы, которые присутствуют в одной папке, но отсутствующих в другой.</span><span class="sxs-lookup"><span data-stu-id="5d42e-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="5d42e-117">Практическое руководство: запрос самого большого файла или файлов в дереве каталогов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="5d42e-118">Описание способов возврата наибольшего или наименьшего файла или определенного числа файлов, в дереве каталогов.</span><span class="sxs-lookup"><span data-stu-id="5d42e-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="5d42e-119">Практическое руководство: запрос повторяющихся файлов в дереве каталогов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="5d42e-120">Описание способов группировки всех имен файлов, находящихся в нескольких местах в указанном дереве каталогов.</span><span class="sxs-lookup"><span data-stu-id="5d42e-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="5d42e-121">Также показано, как для выполнения более сложных сравнений с учетом пользовательского блока сравнения.</span><span class="sxs-lookup"><span data-stu-id="5d42e-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="5d42e-122">Практическое руководство: запрос содержимого файлов в папке (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-122">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="5d42e-123">Показано, как перебора папок в дереве, открытия каждого файла и запроса к содержимому файла.</span><span class="sxs-lookup"><span data-stu-id="5d42e-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="5d42e-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5d42e-124">Comments</span></span>  
 <span data-ttu-id="5d42e-125">Существует некоторые сложности, связанные с созданием источника данных, который точно представляет содержимое файловой системы и корректно обрабатывает исключения.</span><span class="sxs-lookup"><span data-stu-id="5d42e-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="5d42e-126">В примерах этого раздела создается моментальный снимок коллекции из <xref:System.IO.FileInfo>объектов, представляющих все файлы в указанной корневой папке и всех ее подпапках.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5d42e-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="5d42e-127">Фактическое состояние каждого <xref:System.IO.FileInfo>может измениться в период между началом и окончанием выполнения запроса.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5d42e-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="5d42e-128">Например, можно создать список <xref:System.IO.FileInfo>объектов для использования в качестве источника данных.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5d42e-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="5d42e-129">Если при попытке доступа к `Length` свойства в запросе, <xref:System.IO.FileInfo>объекта попытается получить доступ к файловой системе для обновления значения `Length`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5d42e-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="5d42e-130">Если файл больше не существует, вы получите <xref:System.IO.FileNotFoundException>в запросе, даже если вы не выполняется в файловой системе непосредственный запрос.</xref:System.IO.FileNotFoundException></span><span class="sxs-lookup"><span data-stu-id="5d42e-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="5d42e-131">Некоторые запросы в этом разделе используют отдельный метод, который использует эти конкретные исключения в определенных случаях.</span><span class="sxs-lookup"><span data-stu-id="5d42e-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="5d42e-132">Другой возможностью является поддержка источника данных обновленным динамически с помощью <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher></span><span class="sxs-lookup"><span data-stu-id="5d42e-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d42e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5d42e-133">See Also</span></span>  
 [<span data-ttu-id="5d42e-134">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d42e-134">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
