---
title: "Практическое руководство. Перечисление каталогов и файлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="a3c12-102">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="a3c12-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="a3c12-103">Можно перечислить каталоги и файлы с помощью методов, которые возвращают перечисляемую коллекцию строк, представляющих их имена.</span><span class="sxs-lookup"><span data-stu-id="a3c12-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="a3c12-104">Можно также использовать методы, которые возвращают перечисляемую коллекцию <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, или <xref:System.IO.FileSystemInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="a3c12-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="a3c12-105">Перечисляемые коллекции обеспечивают лучшую производительность, чем массивы, при работе с большими коллекциями файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="a3c12-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="a3c12-106">Можно также использовать перечислимые коллекции, полученные из этих методов для предоставления <xref:System.Collections.Generic.IEnumerable%601> параметр для конструкторов коллекции классов, таких как <xref:System.Collections.Generic.List%601> класса.</span><span class="sxs-lookup"><span data-stu-id="a3c12-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="a3c12-107">Если вы хотите получить только имена каталогов или файлов, используйте методы перечисления <xref:System.IO.Directory> класса.</span><span class="sxs-lookup"><span data-stu-id="a3c12-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="a3c12-108">Если вы хотите получить другие свойства каталогов или файлов, используйте <xref:System.IO.DirectoryInfo> и <xref:System.IO.FileSystemInfo> классы.</span><span class="sxs-lookup"><span data-stu-id="a3c12-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="a3c12-109">Ниже приводится руководство по методы, которые возвращают перечислимые коллекции.</span><span class="sxs-lookup"><span data-stu-id="a3c12-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="a3c12-110">Для перечисления</span><span class="sxs-lookup"><span data-stu-id="a3c12-110">To enumerate</span></span>|<span data-ttu-id="a3c12-111">Перечисляемая коллекция для возврата</span><span class="sxs-lookup"><span data-stu-id="a3c12-111">Enumerable collection to return</span></span>|<span data-ttu-id="a3c12-112">Метод, используемый</span><span class="sxs-lookup"><span data-stu-id="a3c12-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="a3c12-113">Каталоги</span><span class="sxs-lookup"><span data-stu-id="a3c12-113">Directories</span></span>|<span data-ttu-id="a3c12-114">Имена каталогов</span><span class="sxs-lookup"><span data-stu-id="a3c12-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="a3c12-115">Сведения о каталоге (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="a3c12-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a3c12-116">Файлы</span><span class="sxs-lookup"><span data-stu-id="a3c12-116">Files</span></span>|<span data-ttu-id="a3c12-117">Имена файлов</span><span class="sxs-lookup"><span data-stu-id="a3c12-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="a3c12-118">Сведения о файлах (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="a3c12-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a3c12-119">Сведения о файловой системе</span><span class="sxs-lookup"><span data-stu-id="a3c12-119">File system information</span></span>|<span data-ttu-id="a3c12-120">Элементы системного файла</span><span class="sxs-lookup"><span data-stu-id="a3c12-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="a3c12-121">Файл сведений о системе (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="a3c12-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="a3c12-122">Несмотря на то, что можно немедленно выполнить перечисление всех файлов во вложенных каталогах родительского каталога с помощью <xref:System.IO.SearchOption.AllDirectories> поиска, предоставляемые параметр <xref:System.IO.SearchOption> перечисления, исключения несанкционированного доступа (<xref:System.UnauthorizedAccessException>) может привести к перечисления не была завершена.</span><span class="sxs-lookup"><span data-stu-id="a3c12-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="a3c12-123">Если эти исключения возможны, можно перехватить и продолжить, сначала перечисление каталогов и затем перечисление файлов.</span><span class="sxs-lookup"><span data-stu-id="a3c12-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="a3c12-124">Перечисление имен каталогов</span><span class="sxs-lookup"><span data-stu-id="a3c12-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="a3c12-125">Используйте <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> метод, чтобы получить список имен каталогов верхнего уровня по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="a3c12-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="a3c12-126">Перечисление имен файлов в каталоге и подкаталогах</span><span class="sxs-lookup"><span data-stu-id="a3c12-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="a3c12-127">Используйте <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> метод для поиска и (необязательно) его подкаталогов каталога и получить список имен файлов, соответствующих указанному шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="a3c12-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="a3c12-128">Перечисление коллекции объектов DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="a3c12-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="a3c12-129">Используйте <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> метод для получения коллекции каталогов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="a3c12-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="a3c12-130">Перечисление коллекции объектов FileInfo во всех каталогах</span><span class="sxs-lookup"><span data-stu-id="a3c12-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="a3c12-131">Используйте <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> метод, чтобы получить коллекцию файлов, которые соответствуют указанному шаблону поиска во всех каталогах.</span><span class="sxs-lookup"><span data-stu-id="a3c12-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="a3c12-132">В этом примере сначала Перечисляет каталоги верхнего уровня для перехвата возможных исключений несанкционированного доступа и затем выполняется перечисление файлов.</span><span class="sxs-lookup"><span data-stu-id="a3c12-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a3c12-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a3c12-133">See Also</span></span>  
 [<span data-ttu-id="a3c12-134">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="a3c12-134">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
