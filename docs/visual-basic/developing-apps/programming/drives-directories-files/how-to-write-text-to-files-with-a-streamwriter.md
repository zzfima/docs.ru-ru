---
title: "Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic"
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
- writing to files, StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
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
ms.openlocfilehash: ea85d57e9af4fdd640733db5dc2fa8b0ab25325c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="b8ff3-102">Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8ff3-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="b8ff3-103">В этом примере с помощью метода `My.Computer.FileSystem.OpenTextFileWriter` открывается объект <xref:System.IO.StreamWriter>, который используется для записи строки в текстовый файл с помощью метода <xref:System.IO.TextWriter.WriteLine%2A> класса <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="b8ff3-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8ff3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b8ff3-104">Example</span></span>  
 <span data-ttu-id="b8ff3-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8ff3-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b8ff3-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="b8ff3-106">Robust Programming</span></span>  
 <span data-ttu-id="b8ff3-107">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="b8ff3-107">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b8ff3-108">Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b8ff3-108">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="b8ff3-109">Диск заполнен (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b8ff3-109">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="b8ff3-110">Слишком длинное имя пути (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b8ff3-110">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b8ff3-111">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b8ff3-111">.NET Framework Security</span></span>  
 <span data-ttu-id="b8ff3-112">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="b8ff3-112">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="b8ff3-113">Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`).</span><span class="sxs-lookup"><span data-stu-id="b8ff3-113">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="b8ff3-114">Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии.</span><span class="sxs-lookup"><span data-stu-id="b8ff3-114">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="b8ff3-115">Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.</span><span class="sxs-lookup"><span data-stu-id="b8ff3-115">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ff3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b8ff3-116">See Also</span></span>  
 <span data-ttu-id="b8ff3-117"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="b8ff3-117"><xref:System.IO.StreamWriter></span></span>   
 <span data-ttu-id="b8ff3-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="b8ff3-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="b8ff3-119">[Практическое руководство. Чтение из текстовых файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="b8ff3-119">[How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span></span>  
 [<span data-ttu-id="b8ff3-120">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="b8ff3-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

