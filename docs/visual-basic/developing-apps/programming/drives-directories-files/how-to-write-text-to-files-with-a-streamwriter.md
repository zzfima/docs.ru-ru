---
title: "Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 874bb9cb88bbf25cb6208a0a33858855a7b26a49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="e13d1-102">Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e13d1-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="e13d1-103">В этом примере с помощью метода `My.Computer.FileSystem.OpenTextFileWriter` открывается объект <xref:System.IO.StreamWriter>, который используется для записи строки в текстовый файл с помощью метода <xref:System.IO.TextWriter.WriteLine%2A> класса <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="e13d1-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e13d1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e13d1-104">Example</span></span>  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e13d1-105">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e13d1-105">Robust Programming</span></span>  
 <span data-ttu-id="e13d1-106">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="e13d1-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e13d1-107">Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e13d1-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e13d1-108">Диск заполнен (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e13d1-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e13d1-109">Слишком длинное имя пути (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="e13d1-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e13d1-110">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e13d1-110">.NET Framework Security</span></span>  
 <span data-ttu-id="e13d1-111">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="e13d1-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="e13d1-112">Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`).</span><span class="sxs-lookup"><span data-stu-id="e13d1-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="e13d1-113">Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии.</span><span class="sxs-lookup"><span data-stu-id="e13d1-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="e13d1-114">Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.</span><span class="sxs-lookup"><span data-stu-id="e13d1-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13d1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e13d1-115">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>  
 [<span data-ttu-id="e13d1-116">Практическое руководство. Чтение из текстовых файлов</span><span class="sxs-lookup"><span data-stu-id="e13d1-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)  
 [<span data-ttu-id="e13d1-117">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="e13d1-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
