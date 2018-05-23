---
title: Практическое руководство. Создание копии файла в другом каталоге в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: 1584e2a768562670662d3a9636d23f0ffe38547e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a><span data-ttu-id="6c362-102">Практическое руководство. Создание копии файла в другом каталоге в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6c362-102">How to: Create a Copy of a File in a Different Directory in Visual Basic</span></span>
<span data-ttu-id="6c362-103">Метод `My.Computer.FileSystem.CopyFile` позволяет копировать файлы.</span><span class="sxs-lookup"><span data-stu-id="6c362-103">The `My.Computer.FileSystem.CopyFile` method allows you to copy files.</span></span> <span data-ttu-id="6c362-104">Его параметры обеспечивают возможность перезаписи существующих файлов, переименования файлов и отображения хода выполнения операции, а также отмены операции пользователем.</span><span class="sxs-lookup"><span data-stu-id="6c362-104">Its parameters provide the ability to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-copy-a-text-file-to-another-folder"></a><span data-ttu-id="6c362-105">Копирование текстового файла в другую папку</span><span class="sxs-lookup"><span data-stu-id="6c362-105">To copy a text file to another folder</span></span>  
  
-   <span data-ttu-id="6c362-106">Используйте для копирования файла метод `CopyFile`, исходный файл и целевой каталог.</span><span class="sxs-lookup"><span data-stu-id="6c362-106">Use the `CopyFile` method to copy a file, specifying a source file and the target directory.</span></span> <span data-ttu-id="6c362-107">Параметр `overwrite` позволяет указать, следует ли перезаписывать существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="6c362-107">The `overwrite` parameter allows you to specify whether or not to overwrite existing files.</span></span> <span data-ttu-id="6c362-108">В следующем примере кода демонстрируется использование метода `CopyFile`.</span><span class="sxs-lookup"><span data-stu-id="6c362-108">The following code examples demonstrate how to use `CopyFile`.</span></span>  
  
     [!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6c362-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="6c362-109">Robust Programming</span></span>  
 <span data-ttu-id="6c362-110">Исключение может возникнуть в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="6c362-110">The following conditions may cause an exception to be thrown:</span></span>  
  
-   <span data-ttu-id="6c362-111">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-111">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="6c362-112">Системе не удалось получить абсолютный путь (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-112">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="6c362-113">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="6c362-114">Исходный файл является недопустимым или не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-114">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="6c362-115">Объединенный путь указывает на существующий каталог (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-115">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="6c362-116">Конечный файл существует, а параметр `overwrite` имеет значение `False` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-116">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="6c362-117">Пользователь не имеет необходимых разрешений для доступа к файлу (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-117">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="6c362-118">Файл в папке назначения с тем же именем уже используется (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-118">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="6c362-119">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="6c362-120">Параметр `ShowUI` имеет значение `True`, параметр `onUserCancel` имеет значение `ThrowException`, и пользователь отменил операцию (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-120">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="6c362-121">`ShowUI` имеет значение `True`, параметр `onUserCancel` имеет значение `ThrowException`, и возникла неопределенная ошибка ввода-вывода (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-121">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="6c362-122">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="6c362-123">У пользователя отсутствует необходимое разрешение (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="6c362-124">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="6c362-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c362-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6c362-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>  
 [<span data-ttu-id="6c362-126">Практическое руководство. Копирование файлов по заданному шаблону в каталог</span><span class="sxs-lookup"><span data-stu-id="6c362-126">How to: Copy Files with a Specific Pattern to a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)  
 [<span data-ttu-id="6c362-127">Практическое руководство. Создание копии файла в том же каталоге</span><span class="sxs-lookup"><span data-stu-id="6c362-127">How to: Create a Copy of a File in the Same Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)  
 [<span data-ttu-id="6c362-128">Практическое руководство. Копирование каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="6c362-128">How to: Copy a Directory to Another Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)  
 [<span data-ttu-id="6c362-129">Практическое руководство. Переименование файла</span><span class="sxs-lookup"><span data-stu-id="6c362-129">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
