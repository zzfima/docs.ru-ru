---
title: "Практическое руководство. Запись текста в файлы в Visual Basic"
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
- files, writing to
- text, writing to files
- writing to files
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
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
ms.openlocfilehash: dc6f02d6092a30113b8cb973be225e140eca19ad
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-in-visual-basic"></a><span data-ttu-id="191bd-102">Практическое руководство. Запись текста в файлы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="191bd-102">How to: Write Text to Files in Visual Basic</span></span>
<span data-ttu-id="191bd-103">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> можно использовать для записи текста в файлы.</span><span class="sxs-lookup"><span data-stu-id="191bd-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to write text to files.</span></span> <span data-ttu-id="191bd-104">Если заданный файл не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="191bd-104">If the specified file does not exist, it is created.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="191bd-105">Процедура</span><span class="sxs-lookup"><span data-stu-id="191bd-105">Procedure</span></span>  
  
#### <a name="to-write-text-to-a-file"></a><span data-ttu-id="191bd-106">Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="191bd-106">To write text to a file</span></span>  
  
-   <span data-ttu-id="191bd-107">Используйте `WriteAllText` метод для записи текста в файл, указав файл и текст, который требуется записать.</span><span class="sxs-lookup"><span data-stu-id="191bd-107">Use the `WriteAllText` method to write text to a file, specifying the file and text to be written.</span></span> <span data-ttu-id="191bd-108">В этом примере строка `"This is new text."` записывается в файл с именем `test.txt`, при этом текст добавляется к тексту, имеющемуся в файле.</span><span class="sxs-lookup"><span data-stu-id="191bd-108">This example writes the line `"This is new text."` to the file named `test.txt`, appending the text to any existing text in the file.</span></span>  
  
     <span data-ttu-id="191bd-109">[!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="191bd-109">[!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]</span></span>  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a><span data-ttu-id="191bd-110">Запись набора строк в файл</span><span class="sxs-lookup"><span data-stu-id="191bd-110">To write a series of strings to a file</span></span>  
  
-   <span data-ttu-id="191bd-111">Выполните цикл по коллекции строк.</span><span class="sxs-lookup"><span data-stu-id="191bd-111">Loop through the string collection.</span></span> <span data-ttu-id="191bd-112">Используйте `WriteAllText` метод для записи текста в файл, указав конечный файл и строку, которую требуется добавить, и присвоив параметру `append` значение `True`.</span><span class="sxs-lookup"><span data-stu-id="191bd-112">Use the `WriteAllText` method to write text to a file, specifying the target file and string to be added and setting `append` to `True`.</span></span>  
  
     <span data-ttu-id="191bd-113">В этом примере имена файлов в каталоге `Documents and Settings` записываются в файл `FileList.txt`, при этом между каждой записью вставляется символ перевода строки для удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="191bd-113">This example writes the names of the files in the `Documents and Settings` directory to `FileList.txt`, inserting a carriage return between each for better readability.</span></span>  
  
     <span data-ttu-id="191bd-114">[!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="191bd-114">[!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="191bd-115">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="191bd-115">Robust Programming</span></span>  
 <span data-ttu-id="191bd-116">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="191bd-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="191bd-117">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="191bd-118">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="191bd-119">`File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-119">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="191bd-120">Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-120">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="191bd-121">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="191bd-122">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="191bd-123">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="191bd-124">Диск заполнен, и вызов `WriteAllText` завершается сбоем (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="191bd-124">The disk is full, and the call to `WriteAllText` fails (<xref:System.IO.IOException>).</span></span>  
  
 <span data-ttu-id="191bd-125">Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа.</span><span class="sxs-lookup"><span data-stu-id="191bd-125">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="191bd-126">Дополнительные сведения см. в разделе [Основы управления доступом для кода](https://msdn.microsoft.com/library/33tceax8).</span><span class="sxs-lookup"><span data-stu-id="191bd-126">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191bd-127">См. также</span><span class="sxs-lookup"><span data-stu-id="191bd-127">See Also</span></span>  
 <span data-ttu-id="191bd-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="191bd-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="191bd-129"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span><span class="sxs-lookup"><span data-stu-id="191bd-129"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span></span>   
 [<span data-ttu-id="191bd-130">Практическое руководство. Чтение из текстовых файлов</span><span class="sxs-lookup"><span data-stu-id="191bd-130">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)

