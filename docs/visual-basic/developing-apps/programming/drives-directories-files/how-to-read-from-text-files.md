---
title: Практическое руководство. Чтение из текстовых файлов
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 8af088ad269cc77bc5c83aedb86bde9af2e37a15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334592"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a><span data-ttu-id="6a4e4-102">Практическое руководство. Чтение из текстовых файлов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a4e4-102">How to: Read From Text Files in Visual Basic</span></span>

<span data-ttu-id="6a4e4-103">Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> объекта `My.Computer.FileSystem` позволяет считывать данные из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> method of the `My.Computer.FileSystem` object allows you to read from a text file.</span></span> <span data-ttu-id="6a4e4-104">Если содержимое файла имеет определенную кодировку, например ASCII или UTF-8, ее можно указать в аргументе.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-104">The file encoding can be specified if the contents of the file use an encoding such as ASCII or UTF-8.</span></span>

<span data-ttu-id="6a4e4-105">Если вы производите чтение из файла с символами национальных алфавитов, необходимо указать кодировку файла.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-105">If you are reading from a file with extended characters, you will need to specify the file encoding.</span></span>

> [!NOTE]
> <span data-ttu-id="6a4e4-106">Чтобы прочитать файл по одной строке, используйте метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> объекта `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-106">To read a file a single line of text at a time, use the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> method of the `My.Computer.FileSystem` object.</span></span> <span data-ttu-id="6a4e4-107">Метод `OpenTextFileReader` возвращает объект <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-107">The `OpenTextFileReader` method returns a <xref:System.IO.StreamReader> object.</span></span> <span data-ttu-id="6a4e4-108">С помощью метода <xref:System.IO.StreamReader.ReadLine%2A> объекта `StreamReader` можно прочитать файл по одной строке.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-108">You can use the <xref:System.IO.StreamReader.ReadLine%2A> method of the `StreamReader` object to read a file one line at a time.</span></span> <span data-ttu-id="6a4e4-109">Проверить, достигнут ли конец файла, можно с помощью метода <xref:System.IO.StreamReader.EndOfStream%2A> объекта `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-109">You can test for the end of the file using the <xref:System.IO.StreamReader.EndOfStream%2A> method of the `StreamReader` object.</span></span>

## <a name="to-read-from-a-text-file"></a><span data-ttu-id="6a4e4-110">Чтение данных из текстового файла</span><span class="sxs-lookup"><span data-stu-id="6a4e4-110">To read from a text file</span></span>

<span data-ttu-id="6a4e4-111">Для считывания содержимого текстового файла в строку используйте метод `ReadAllText` объекта `My.Computer.FileSystem`, указав путь.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-111">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path.</span></span> <span data-ttu-id="6a4e4-112">В следующем примере содержимое файла test.txt считывается в строку и затем отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-112">The following example reads the contents of test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a><span data-ttu-id="6a4e4-113">Чтение данных из зашифрованного текстового файла</span><span class="sxs-lookup"><span data-stu-id="6a4e4-113">To read from a text file that is encoded</span></span>

<span data-ttu-id="6a4e4-114">Для считывания содержимого текстового файла в строку используйте метод `ReadAllText` объекта `My.Computer.FileSystem`, указав путь и тип кодировки файла.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-114">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path and file encoding type.</span></span> <span data-ttu-id="6a4e4-115">В следующем примере содержимое файла test.txt в кодировке UTF32 считывается в строку и затем отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-115">The following example reads the contents of the UTF32 file test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a><span data-ttu-id="6a4e4-116">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="6a4e4-116">Robust Programming</span></span>

<span data-ttu-id="6a4e4-117">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="6a4e4-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="6a4e4-118">Путь является недопустимым, поскольку путь представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-118">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="6a4e4-119">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-119">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="6a4e4-120">Файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-120">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>

- <span data-ttu-id="6a4e4-121">Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-121">The file is in use by another process or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="6a4e4-122">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="6a4e4-123">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-123">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="6a4e4-124">Не хватает памяти для записи строки в буфер (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-124">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>

- <span data-ttu-id="6a4e4-125">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="6a4e4-125">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

<span data-ttu-id="6a4e4-126">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-126">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="6a4e4-127">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-127">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>

<span data-ttu-id="6a4e4-128">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-128">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="6a4e4-129">Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.</span><span class="sxs-lookup"><span data-stu-id="6a4e4-129">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a4e4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6a4e4-130">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [<span data-ttu-id="6a4e4-131">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="6a4e4-131">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="6a4e4-132">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="6a4e4-132">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="6a4e4-133">Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="6a4e4-133">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="6a4e4-134">Практическое руководство. Чтение из текстовых файлов различных форматов</span><span class="sxs-lookup"><span data-stu-id="6a4e4-134">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="6a4e4-135">Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы</span><span class="sxs-lookup"><span data-stu-id="6a4e4-135">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="6a4e4-136">Пошаговое руководство: Операции с файлами и каталогами в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a4e4-136">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="6a4e4-137">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="6a4e4-137">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
