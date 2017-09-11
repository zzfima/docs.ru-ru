---
title: "Практическое руководство. Запись текста в двоичные файлы в Visual Basic"
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
- files, binary access
- WriteAllBytes method
- binary files, writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
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
ms.openlocfilehash: ae6f275dd86a53c6b6251feb08210a775adba0b0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="c7435-102">Практическое руководство. Запись текста в двоичные файлы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7435-102">How to: Write to Binary Files in Visual Basic</span></span>
<span data-ttu-id="c7435-103">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> записывает данные в двоичный файл.</span><span class="sxs-lookup"><span data-stu-id="c7435-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="c7435-104">Если параметр `append` имеет значение `True`, данные будут добавляться в файл; в противном случае данные в файле перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="c7435-104">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>  
  
 <span data-ttu-id="c7435-105">Если указанный путь без имени файла является недопустимым, возникает исключение <xref:System.IO.DirectoryNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="c7435-105">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="c7435-106">Если путь является допустимым, но файл не существует, файл будет создан.</span><span class="sxs-lookup"><span data-stu-id="c7435-106">If the path is valid but the file does not exist, the file will be created.</span></span>  
  
### <a name="to-write-to-a-binary-file"></a><span data-ttu-id="c7435-107">Запись в двоичный файл</span><span class="sxs-lookup"><span data-stu-id="c7435-107">To write to a binary file</span></span>  
  
-   <span data-ttu-id="c7435-108">Используйте метод `WriteAllBytes`, указав путь к файлу, имя файла и байты, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="c7435-108">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="c7435-109">В этом примере массив данных `CustomerData` добавляется в файл `CollectedData.dat`.</span><span class="sxs-lookup"><span data-stu-id="c7435-109">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>  
  
     <span data-ttu-id="c7435-110">[!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c7435-110">[!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c7435-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="c7435-111">Robust Programming</span></span>  
 <span data-ttu-id="c7435-112">Исключение может возникнуть при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="c7435-112">The following conditions may create an exception:</span></span>  
  
-   <span data-ttu-id="c7435-113">Путь является недопустимым по одной из следующих причин: это строка нулевой длины; она содержит только пробелы; она содержит недопустимые знаки.</span><span class="sxs-lookup"><span data-stu-id="c7435-113">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="c7435-114">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-114">(<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="c7435-115">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="c7435-116">`File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-116">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="c7435-117">Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-117">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="c7435-118">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="c7435-119">Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="c7435-120">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c7435-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7435-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c7435-121">See Also</span></span>  
 <span data-ttu-id="c7435-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A></span><span class="sxs-lookup"><span data-stu-id="c7435-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A></span></span>   
 [<span data-ttu-id="c7435-123">Практическое руководство. Запись текста в файлы</span><span class="sxs-lookup"><span data-stu-id="c7435-123">How to: Write Text to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)

