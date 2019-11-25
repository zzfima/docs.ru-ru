---
title: Практическое руководство. Копирование каталога в другой каталог
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
ms.openlocfilehash: a23079f093f53ab8e20eb71c684a594dcf7f894b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348861"
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="19066-102">Практическое руководство. Копирование каталога в другой каталог в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19066-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>

<span data-ttu-id="19066-103">Используйте метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> для копирования каталога в другой каталог.</span><span class="sxs-lookup"><span data-stu-id="19066-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="19066-104">Этот метод копирует и содержимое каталога, и сам каталог.</span><span class="sxs-lookup"><span data-stu-id="19066-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="19066-105">Если целевой каталог не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="19066-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="19066-106">Если каталог с тем же именем уже существует в целевом расположении, а параметр `overwrite` имеет значение `False`, содержимое двух каталогов будут объединено.</span><span class="sxs-lookup"><span data-stu-id="19066-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="19066-107">Во время операции можно указать новое имя для каталога.</span><span class="sxs-lookup"><span data-stu-id="19066-107">You can specify a new name for the directory during the operation.</span></span>

<span data-ttu-id="19066-108">При копировании файлов в каталоге могут возникать исключения, вызываемые определенным файлом, например файлом, существующим во время слияния, если параметр `overwrite` имеет значение `False`.</span><span class="sxs-lookup"><span data-stu-id="19066-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="19066-109">Если такие исключения возникают, они объединяются в общее исключение. Свойство `Data` этого исключения содержит записи, в которых путь к файлу и каталогу является ключом, а соответствующее значение содержит сведения о конкретном исключении.</span><span class="sxs-lookup"><span data-stu-id="19066-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>

## <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="19066-110">Копирование каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="19066-110">To copy a directory to another directory</span></span>

- <span data-ttu-id="19066-111">Воспользуйтесь методом `CopyDirectory`, указав имена исходного и целевого каталогов.</span><span class="sxs-lookup"><span data-stu-id="19066-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="19066-112">Представленный в приведенном ниже примере код копирует каталог с именем `TestDirectory1` в `TestDirectory2`, перезаписывая существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="19066-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>

    [!code-vb[VbVbcnMyFileSystem#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#16)]

    <span data-ttu-id="19066-113">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="19066-113">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="19066-114">В средстве выбора фрагментов кода он находится в разделе **Файловая система: обработка дисков, папок и файлов**.</span><span class="sxs-lookup"><span data-stu-id="19066-114">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="19066-115">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="19066-115">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>

## <a name="robust-programming"></a><span data-ttu-id="19066-116">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="19066-116">Robust Programming</span></span>

<span data-ttu-id="19066-117">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="19066-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="19066-118">Новое имя, указанное для каталога, содержит двоеточие (:) или косую черту (\ или /) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="19066-118">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="19066-119">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="19066-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="19066-120">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="19066-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="19066-121">Параметр `destinationDirectoryName` имеет значение `Nothing` или является пустой строкой (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="19066-121">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>

- <span data-ttu-id="19066-122">Целевой каталог не существует (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="19066-122">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="19066-123">Исходный каталог является корневым каталогом (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="19066-123">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="19066-124">Объединенный путь указывает на существующий файл (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="19066-124">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="19066-125">Исходный и конечный пути совпадают (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="19066-125">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="19066-126">`ShowUI` имеет значение `UIOption.AllDialogs`, а пользователь отменяет операцию, либо невозможно скопировать один или несколько файлов в каталоге (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="19066-126">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>

- <span data-ttu-id="19066-127">Операция является циклической (<xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="19066-127">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>

- <span data-ttu-id="19066-128">Путь содержит двоеточие (:) (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="19066-128">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="19066-129">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="19066-129">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="19066-130">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="19066-130">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="19066-131">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="19066-131">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="19066-132">Конечный файл существует, но недоступен (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="19066-132">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="19066-133">См. также</span><span class="sxs-lookup"><span data-stu-id="19066-133">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>
- [<span data-ttu-id="19066-134">Практическое руководство. Поиск подкаталогов по заданному шаблону</span><span class="sxs-lookup"><span data-stu-id="19066-134">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="19066-135">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="19066-135">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
