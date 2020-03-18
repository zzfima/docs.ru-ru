---
title: Практическое руководство. Чтение из двоичного файла
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: c33bc72a5c79901e3715ed6a587ffdb8e3565e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335291"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="f10a8-102">Практическое руководство. Чтение из двоичного файла в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f10a8-102">How to: Read From Binary Files in Visual Basic</span></span>

<span data-ttu-id="f10a8-103">Объект `My.Computer.FileSystem` предоставляет метод `ReadAllBytes` для чтения данных из двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="f10a8-103">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="f10a8-104">Чтение данных из двоичного файла</span><span class="sxs-lookup"><span data-stu-id="f10a8-104">To read from a binary file</span></span>  
  
- <span data-ttu-id="f10a8-105">Используйте метод `ReadAllBytes`, который возвращает содержимое файла в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="f10a8-105">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="f10a8-106">В этом примере производится чтение данных из файла `C:/Documents and Settings/selfportrait.jpg`.</span><span class="sxs-lookup"><span data-stu-id="f10a8-106">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#78)]  
  
- <span data-ttu-id="f10a8-107">При работе с большими двоичными файлами можно использовать метод <xref:System.IO.FileStream.Read%2A> объекта <xref:System.IO.FileStream>, чтобы за раз считывать из файла только заданный объем данных.</span><span class="sxs-lookup"><span data-stu-id="f10a8-107">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="f10a8-108">Затем можно ограничить объем файла, загружаемый в память во время каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="f10a8-108">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="f10a8-109">В следующем примере кода показано копирование файла, причем вызывающий объект задает, какая часть файла помещается в память при выполнении каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="f10a8-109">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#91)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f10a8-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f10a8-110">Robust Programming</span></span>  

 <span data-ttu-id="f10a8-111">Исключение может возникнуть в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f10a8-111">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="f10a8-112">Путь является недопустимым, поскольку путь представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="f10a8-113">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="f10a8-114">Файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-114">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="f10a8-115">Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-115">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="f10a8-116">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-116">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="f10a8-117">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-117">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="f10a8-118">Не хватает памяти для записи строки в буфер (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-118">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
- <span data-ttu-id="f10a8-119">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f10a8-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="f10a8-120">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="f10a8-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="f10a8-121">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f10a8-121">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="f10a8-122">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="f10a8-122">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="f10a8-123">Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.</span><span class="sxs-lookup"><span data-stu-id="f10a8-123">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10a8-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f10a8-124">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="f10a8-125">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="f10a8-125">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="f10a8-126">Практическое руководство. Чтение из текстовых файлов различных форматов</span><span class="sxs-lookup"><span data-stu-id="f10a8-126">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="f10a8-127">Запись данных в буфер обмена и чтение их оттуда</span><span class="sxs-lookup"><span data-stu-id="f10a8-127">Storing Data to and Reading from the Clipboard</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
