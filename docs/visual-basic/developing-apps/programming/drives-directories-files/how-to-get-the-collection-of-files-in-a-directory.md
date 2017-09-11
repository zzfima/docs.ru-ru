---
title: "Практическое руководство. Получение коллекции содержащихся в каталоге файлов в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- folders, working with
- files, accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 023fb90622b45fe0067cd146f62bc3edb326b5ef
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a><span data-ttu-id="8e35a-102">Практическое руководство. Получение коллекции содержащихся в каталоге файлов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e35a-102">How to: Get the Collection of Files in a Directory in Visual Basic</span></span>
<span data-ttu-id="8e35a-103">Перегрузка метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> вернет доступную только для чтения коллекцию строк, представляющих собой имена файлов в каталоге:</span><span class="sxs-lookup"><span data-stu-id="8e35a-103">The overloads of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> method return a read-only collection of strings representing the names of the files within a directory:</span></span>  
  
-   <span data-ttu-id="8e35a-104">Перегрузка метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> позволяет найти простой файл в указанном каталоге без поиска подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="8e35a-104">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> overload for a simple file search in a specified directory, without searching subdirectories.</span></span>  
  
-   <span data-ttu-id="8e35a-105">Перегрузка метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> позволяет указать дополнительные параметры поиска.</span><span class="sxs-lookup"><span data-stu-id="8e35a-105">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> overload to specify additional options for your search.</span></span> <span data-ttu-id="8e35a-106">Для указания шаблона поиска можно использовать параметр `wildCards`.</span><span class="sxs-lookup"><span data-stu-id="8e35a-106">You can use the `wildCards` parameter to specify a search pattern.</span></span> <span data-ttu-id="8e35a-107">Чтобы включить подкаталоги в поиск, присвойте параметру `searchType` значение <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8e35a-107">To include subdirectories in the search, set the `searchType` parameter to <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="8e35a-108">Если файлы, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.</span><span class="sxs-lookup"><span data-stu-id="8e35a-108">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
### <a name="to-list-files-in-a-directory"></a><span data-ttu-id="8e35a-109">Составление списка файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="8e35a-109">To list files in a directory</span></span>  
  
-   <span data-ttu-id="8e35a-110">Используйте перегрузки одного из методов <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName>, указывая имя и путь к каталогу для поиска в параметре `directory`.</span><span class="sxs-lookup"><span data-stu-id="8e35a-110">Use one of the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> method overloads, supplying the name and path of the directory to search in the `directory` parameter.</span></span> <span data-ttu-id="8e35a-111">В следующем примере возвращаются и добавляются в список `ListBox1` все файлы, находящиеся в каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e35a-111">The following example returns all files in the directory and adds them to `ListBox1`.</span></span>  
  
     <span data-ttu-id="8e35a-112">[!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e35a-112">[!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8e35a-113">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8e35a-113">Robust Programming</span></span>  
 <span data-ttu-id="8e35a-114">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="8e35a-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8e35a-115">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="8e35a-116">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="8e35a-117">`directory` не существует (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-117">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="8e35a-118">`directory` указывает на существующий файл (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-118">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="8e35a-119">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="8e35a-120">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="8e35a-121">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="8e35a-122">У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="8e35a-122">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e35a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8e35a-123">See Also</span></span>  
 <span data-ttu-id="8e35a-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A></span><span class="sxs-lookup"><span data-stu-id="8e35a-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A></span></span>   
 <span data-ttu-id="8e35a-125">[Практическое руководство. Поиск файлов по конкретному шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="8e35a-125">[How to: Find Files with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md) </span></span>  
 [<span data-ttu-id="8e35a-126">Практическое руководство. Поиск подкаталогов по шаблону</span><span class="sxs-lookup"><span data-stu-id="8e35a-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)

