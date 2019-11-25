---
title: Практическое руководство. Копирование файлов с определенным шаблоном в каталог
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: ee3951e967436a1b8aec09b8e42dc6d1b547bc02
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348851"
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="eb1b5-102">Практическое руководство. Копирование файлов в каталог с использованием шаблона в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eb1b5-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>

<span data-ttu-id="eb1b5-103">Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей для файлов.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="eb1b5-104">Для указания определенного шаблона можно использовать параметр `wildCards` .</span><span class="sxs-lookup"><span data-stu-id="eb1b5-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="eb1b5-105">Если соответствующие файлы не найдены, возвращается пустая коллекция.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="eb1b5-106">Для копирования файлов в каталог можно использовать метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> .</span><span class="sxs-lookup"><span data-stu-id="eb1b5-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="eb1b5-107">Копирование файлов с определенным шаблоном в каталог</span><span class="sxs-lookup"><span data-stu-id="eb1b5-107">To copy files with a specific pattern to a directory</span></span>  
  
1. <span data-ttu-id="eb1b5-108">Используйте метод `GetFiles` для возврата списка файлов.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="eb1b5-109">В этом примере возвращены все RTF-файлы в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     [!code-vb[VbFileIOMisc#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#36)]  
  
2. <span data-ttu-id="eb1b5-110">Используйте метод `CopyFile` для копирования файлов.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-110">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="eb1b5-111">В этом примере файлы копируются в каталог с именем `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-111">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#88)]  
  
3. <span data-ttu-id="eb1b5-112">Закройте оператор `For` с помощью оператора `Next` .</span><span class="sxs-lookup"><span data-stu-id="eb1b5-112">Close the `For` statement with a `Next` statement.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#89)]  
  
## <a name="example"></a><span data-ttu-id="eb1b5-113">Пример</span><span class="sxs-lookup"><span data-stu-id="eb1b5-113">Example</span></span>  

 <span data-ttu-id="eb1b5-114">В следующем примере, который представляет вышеописанные фрагменты в завершенной форме, RTF-файлы копируются из указанного каталога в каталог с именем `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-114">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 [!code-vb[VbFileIOMisc#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#37)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="eb1b5-115">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eb1b5-115">.NET Framework Security</span></span>  

 <span data-ttu-id="eb1b5-116">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="eb1b5-116">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="eb1b5-117">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="eb1b5-118">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="eb1b5-119">Каталог не существует (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-119">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="eb1b5-120">Каталог указывает на существующий файл (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-120">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="eb1b5-121">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="eb1b5-122">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="eb1b5-123">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="eb1b5-124">У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-124">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1b5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="eb1b5-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [<span data-ttu-id="eb1b5-126">Практическое руководство. Поиск подкаталогов по заданному шаблону</span><span class="sxs-lookup"><span data-stu-id="eb1b5-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="eb1b5-127">Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы</span><span class="sxs-lookup"><span data-stu-id="eb1b5-127">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="eb1b5-128">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="eb1b5-128">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
