---
title: Практическое руководство. Поиск файлов по конкретному шаблону
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
ms.openlocfilehash: 5faaa16615f52714db3de6853786990265716501
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348760"
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="b17dc-102">Практическое руководство. Поиск файлов по конкретному шаблону в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b17dc-102">How to: Find Files with a Specific Pattern in Visual Basic</span></span>

<span data-ttu-id="b17dc-103">Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей для файлов.</span><span class="sxs-lookup"><span data-stu-id="b17dc-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="b17dc-104">Для указания определенного шаблона можно использовать параметр `wildCards` .</span><span class="sxs-lookup"><span data-stu-id="b17dc-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="b17dc-105">Если требуется включить подкаталоги в поиск, присвойте параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.</span><span class="sxs-lookup"><span data-stu-id="b17dc-105">If you would like to include subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="b17dc-106">Если файлы, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.</span><span class="sxs-lookup"><span data-stu-id="b17dc-106">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b17dc-107">Сведения о возврате списка файлов с помощью класса `DirectoryInfo` пространства имен `System.IO` см. в разделе <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="b17dc-107">For information about returning a file list by using the `DirectoryInfo` class of the `System.IO` namespace, see <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span></span>  
  
### <a name="to-find-files-with-a-specified-pattern"></a><span data-ttu-id="b17dc-108">Поиск файлов по конкретному шаблону</span><span class="sxs-lookup"><span data-stu-id="b17dc-108">To find files with a specified pattern</span></span>  
  
- <span data-ttu-id="b17dc-109">Используйте метод `GetFiles`, указав имя и путь к каталогу, в котором требуется выполнить поиск, и шаблон.</span><span class="sxs-lookup"><span data-stu-id="b17dc-109">Use the `GetFiles` method, supplying the name and path of the directory you want to search and specifying the pattern.</span></span> <span data-ttu-id="b17dc-110">В следующем примере возвращаются все файлы с расширением `.dll`, имеющиеся в каталоге, и добавляются в `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="b17dc-110">The following example returns all files with the extension `.dll` in the directory and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbFileIOMisc#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#4)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="b17dc-111">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b17dc-111">.NET Framework Security</span></span>  

 <span data-ttu-id="b17dc-112">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="b17dc-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="b17dc-113">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="b17dc-114">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="b17dc-115">`directory` не существует (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="b17dc-116">`directory` указывает на существующий файл (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="b17dc-117">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="b17dc-118">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="b17dc-119">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="b17dc-120">У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="b17dc-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17dc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b17dc-121">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [<span data-ttu-id="b17dc-122">Практическое руководство. Поиск подкаталогов по заданному шаблону</span><span class="sxs-lookup"><span data-stu-id="b17dc-122">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="b17dc-123">Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы</span><span class="sxs-lookup"><span data-stu-id="b17dc-123">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="b17dc-124">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="b17dc-124">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
