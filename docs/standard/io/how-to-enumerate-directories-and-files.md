---
title: Практическое руководство. Перечисление каталогов и файлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de83395df9e8c89a92e85b96ddd15e9f0be6ad5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207698"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="23ef9-102">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="23ef9-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="23ef9-103">Чтобы перечислить все каталоги и файлы, вы можете применить методы, которые возвращают перечислимую коллекцию строк с именами объектов.</span><span class="sxs-lookup"><span data-stu-id="23ef9-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="23ef9-104">Также можно использовать методы, которые возвращают перечислимую коллекцию объектов <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> или <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="23ef9-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="23ef9-105">Перечислимые коллекции дают более высокую производительность, чем массивы, если вы работаете с большими коллекциями файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="23ef9-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="23ef9-106">Кроме того, можно использовать перечислимые коллекции, полученные из этих методов, чтобы передавать параметр <xref:System.Collections.Generic.IEnumerable%601> в конструкторы классов коллекций, таких как класс <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="23ef9-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="23ef9-107">Если вы хотите только получить имена каталогов или файлов, используйте методы перечисления из класса <xref:System.IO.Directory>.</span><span class="sxs-lookup"><span data-stu-id="23ef9-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="23ef9-108">Если вы хотите получить другие свойства каталогов или файлов, используйте классы <xref:System.IO.DirectoryInfo> и <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="23ef9-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="23ef9-109">Следующая таблица содержит рекомендации по работе с методами, которые возвращают перечислимые коллекции.</span><span class="sxs-lookup"><span data-stu-id="23ef9-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="23ef9-110">Объект для перечисления</span><span class="sxs-lookup"><span data-stu-id="23ef9-110">To enumerate</span></span>|<span data-ttu-id="23ef9-111">Возвращаемая перечислимая коллекция</span><span class="sxs-lookup"><span data-stu-id="23ef9-111">Enumerable collection to return</span></span>|<span data-ttu-id="23ef9-112">Используемый метод</span><span class="sxs-lookup"><span data-stu-id="23ef9-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="23ef9-113">Каталоги</span><span class="sxs-lookup"><span data-stu-id="23ef9-113">Directories</span></span>|<span data-ttu-id="23ef9-114">Имена каталогов</span><span class="sxs-lookup"><span data-stu-id="23ef9-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="23ef9-115">Сведения о каталогах (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="23ef9-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="23ef9-116">Файлы</span><span class="sxs-lookup"><span data-stu-id="23ef9-116">Files</span></span>|<span data-ttu-id="23ef9-117">Имена файлов</span><span class="sxs-lookup"><span data-stu-id="23ef9-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="23ef9-118">Сведения о файлах (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="23ef9-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="23ef9-119">Сведения о файловой системе</span><span class="sxs-lookup"><span data-stu-id="23ef9-119">File system information</span></span>|<span data-ttu-id="23ef9-120">Элементы файловой системы</span><span class="sxs-lookup"><span data-stu-id="23ef9-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="23ef9-121">Сведения о файловой системе (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="23ef9-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="23ef9-122">Несмотря на то, что у вас есть возможность немедленно перечислить все файлы во вложенных каталогах родительского каталога, применив функцию поиска <xref:System.IO.SearchOption.AllDirectories> из перечисления <xref:System.IO.SearchOption>, это перечисление может оказаться неполным из-за исключений несанкционированного доступа (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="23ef9-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="23ef9-123">Если есть риск таких исключений, следует организовать их перехват, и для продолжения работы сначала перечислить каталоги, а затем файлы в них.</span><span class="sxs-lookup"><span data-stu-id="23ef9-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="23ef9-124">Перечисление имен каталогов</span><span class="sxs-lookup"><span data-stu-id="23ef9-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="23ef9-125">Используйте метод <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>, чтобы получить список имен каталогов верхнего уровня из указанного пути.</span><span class="sxs-lookup"><span data-stu-id="23ef9-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="23ef9-126">Перечисление имен файлов в каталоге и подкаталогах</span><span class="sxs-lookup"><span data-stu-id="23ef9-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="23ef9-127">Используйте метод <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>, чтобы выполнить поиск в каталоге и (необязательно) его подкаталогах и получить список имен файлов, соответствующих указанному шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="23ef9-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="23ef9-128">Перечисление коллекции объектов DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="23ef9-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="23ef9-129">Используйте метод <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>, чтобы получить коллекцию каталогов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="23ef9-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="23ef9-130">Перечисление коллекции объектов FileInfo из всех каталогов</span><span class="sxs-lookup"><span data-stu-id="23ef9-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="23ef9-131">Используйте метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>, чтобы получить коллекцию файлов, имена которых соответствуют указанному шаблону поиска, расположенных из всех каталогов.</span><span class="sxs-lookup"><span data-stu-id="23ef9-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="23ef9-132">В этом примере поиска сначала перечисляются каталоги верхнего уровня, чтобы перехватить все возможные исключения несанкционированного доступа, а затем перечисляются файлы.</span><span class="sxs-lookup"><span data-stu-id="23ef9-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="23ef9-133">См. также</span><span class="sxs-lookup"><span data-stu-id="23ef9-133">See also</span></span>

- [<span data-ttu-id="23ef9-134">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="23ef9-134">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
