---
title: "Практическое руководство. Копирование каталога в другой каталог в Visual Basic"
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
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: 19
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
ms.openlocfilehash: 7bcc7f924d26247b0d0ab30a9ea0fc6d6333b652
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="87f17-102">Практическое руководство. Копирование каталога в другой каталог в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87f17-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>
<span data-ttu-id="87f17-103">Используйте метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> для копирования каталога в другой каталог.</span><span class="sxs-lookup"><span data-stu-id="87f17-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="87f17-104">Этот метод копирует и содержимое каталога, и сам каталог.</span><span class="sxs-lookup"><span data-stu-id="87f17-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="87f17-105">Если целевой каталог не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="87f17-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="87f17-106">Если каталог с тем же именем уже существует в целевом расположении, а параметр `overwrite` имеет значение `False`, содержимое двух каталогов будут объединено.</span><span class="sxs-lookup"><span data-stu-id="87f17-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="87f17-107">Во время операции можно указать новое имя для каталога.</span><span class="sxs-lookup"><span data-stu-id="87f17-107">You can specify a new name for the directory during the operation.</span></span>  
  
 <span data-ttu-id="87f17-108">При копировании файлов в каталоге могут возникать исключения, вызываемые определенным файлом, например файлом, существующим во время слияния, если параметр `overwrite` имеет значение `False`.</span><span class="sxs-lookup"><span data-stu-id="87f17-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="87f17-109">Если такие исключения возникают, они объединяются в общее исключение. Свойство `Data` этого исключения содержит записи, в которых путь к файлу и каталогу является ключом, а соответствующее значение содержит сведения о конкретном исключении.</span><span class="sxs-lookup"><span data-stu-id="87f17-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>  
  
### <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="87f17-110">Копирование каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="87f17-110">To copy a directory to another directory</span></span>  
  
-   <span data-ttu-id="87f17-111">Воспользуйтесь методом `CopyDirectory`, указав имена исходного и целевого каталогов.</span><span class="sxs-lookup"><span data-stu-id="87f17-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="87f17-112">Представленный в приведенном ниже примере код копирует каталог с именем `TestDirectory1` в `TestDirectory2`, перезаписывая существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="87f17-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>  
  
     <span data-ttu-id="87f17-113">[!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="87f17-113">[!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]</span></span>  
  
     <span data-ttu-id="87f17-114">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="87f17-114">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="87f17-115">В средстве выбора фрагментов кода он находится в разделе **Файловая система: обработка дисков, папок и файлов**.</span><span class="sxs-lookup"><span data-stu-id="87f17-115">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="87f17-116">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="87f17-116">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="87f17-117">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="87f17-117">Robust Programming</span></span>  
 <span data-ttu-id="87f17-118">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="87f17-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="87f17-119">Новое имя, указанное для каталога, содержит двоеточие (:) или косую черту (\ или /) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-119">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="87f17-120">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-120">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="87f17-121">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-121">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="87f17-122">Параметр `destinationDirectoryName` имеет значение `Nothing` или является пустой строкой (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-122">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="87f17-123">Целевой каталог не существует (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-123">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="87f17-124">Исходный каталог является корневым каталогом (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-124">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="87f17-125">Объединенный путь указывает на существующий файл (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-125">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="87f17-126">Исходный и конечный пути совпадают (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-126">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="87f17-127">`ShowUI` имеет значение `UIOption.AllDialogs`, а пользователь отменяет операцию, либо невозможно скопировать один или несколько файлов в каталоге (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-127">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="87f17-128">Операция является циклической (<xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-128">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>  
  
-   <span data-ttu-id="87f17-129">Путь содержит двоеточие (:) (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-129">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="87f17-130">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-130">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="87f17-131">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-131">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="87f17-132">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-132">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="87f17-133">Конечный файл существует, но недоступен (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="87f17-133">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f17-134">См. также</span><span class="sxs-lookup"><span data-stu-id="87f17-134">See Also</span></span>  
 <span data-ttu-id="87f17-135"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="87f17-135"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A></span></span>   
 <span data-ttu-id="87f17-136">[Практическое руководство. Поиск подкаталогов по шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="87f17-136">[How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md) </span></span>  
 [<span data-ttu-id="87f17-137">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="87f17-137">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

