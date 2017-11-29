---
title: "Практическое руководство. Дозапись в текстовый файл в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 41ab4491dbc21936c6fbfe9440fcbaeaaac6f1dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-append-to-text-files-in-visual-basic"></a><span data-ttu-id="941c6-102">Практическое руководство. Дозапись в текстовый файл в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="941c6-102">How to: Append to Text Files in Visual Basic</span></span>
<span data-ttu-id="941c6-103">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> можно использовать для добавления данных в текстовый файл, задав для параметра `append` значение `True`.</span><span class="sxs-lookup"><span data-stu-id="941c6-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to append to a text file by specifying that the `append` parameter is set to `True`.</span></span>  
  
### <a name="to-append-to-a-text-file"></a><span data-ttu-id="941c6-104">Добавление данных в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="941c6-104">To append to a text file</span></span>  
  
-   <span data-ttu-id="941c6-105">Используйте метод `WriteAllText`, указав конечный файл и строку, которую требуется добавить, и присвоив параметру `append` значение `True`.</span><span class="sxs-lookup"><span data-stu-id="941c6-105">Use the `WriteAllText` method, specifying the target file and string to be appended and setting the `append` parameter to `True`.</span></span>  
  
     <span data-ttu-id="941c6-106">В этом примере в файл с именем `Testfile.txt` записывается строка `"This is a test string."`.</span><span class="sxs-lookup"><span data-stu-id="941c6-106">This example writes the string `"This is a test string."` to the file named `Testfile.txt`.</span></span>  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="941c6-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="941c6-107">Robust Programming</span></span>  
 <span data-ttu-id="941c6-108">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="941c6-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="941c6-109">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-109">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="941c6-110">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-110">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="941c6-111">`File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-111">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="941c6-112">Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-112">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="941c6-113">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-113">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="941c6-114">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-114">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="941c6-115">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="941c6-115">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941c6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="941c6-116">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 [<span data-ttu-id="941c6-117">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="941c6-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
