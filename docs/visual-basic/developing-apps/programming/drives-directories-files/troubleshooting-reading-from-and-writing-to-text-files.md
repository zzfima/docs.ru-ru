---
title: "Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы (Visual Basic)"
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
- troubleshooting file I/O
- writing text to files, troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files, troubleshooting
- reading text files, troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
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
ms.openlocfilehash: 7f1d26df53445ee9711ebb2840071d2560c5380d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="0cb46-102">Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cb46-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>
<span data-ttu-id="0cb46-103">В этом разделе обсуждаются распространенные проблемы, возникающие при работе с текстовыми файлами, и предлагаются способы их устранения.</span><span class="sxs-lookup"><span data-stu-id="0cb46-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="0cb46-104">Распространенные проблемы</span><span class="sxs-lookup"><span data-stu-id="0cb46-104">Common problems</span></span>  
 <span data-ttu-id="0cb46-105">Чаще всего при работе с текстовыми файлами возникают проблемы, связанные с исключениями безопасности, кодировкой файлов и неверными путями.</span><span class="sxs-lookup"><span data-stu-id="0cb46-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="0cb46-106">Исключения безопасности</span><span class="sxs-lookup"><span data-stu-id="0cb46-106">Security exceptions</span></span>  
 <span data-ttu-id="0cb46-107">Исключение <xref:System.Security.SecurityException> создается в случае ошибки безопасности.</span><span class="sxs-lookup"><span data-stu-id="0cb46-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="0cb46-108">Обычно проблема возникает из-за отсутствия необходимых разрешений и устраняется путем добавления разрешений или работы с файлами в изолированном хранилище.</span><span class="sxs-lookup"><span data-stu-id="0cb46-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="0cb46-109">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="0cb46-109">File encodings</span></span>  
 <span data-ttu-id="0cb46-110">Кодировки файлов (или кодировки символов) определяют отображение символов при обработке текстов.</span><span class="sxs-lookup"><span data-stu-id="0cb46-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="0cb46-111">При неправильной кодировке в текстовом файле могут появиться непредвиденные символы.</span><span class="sxs-lookup"><span data-stu-id="0cb46-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="0cb46-112">Для большинства файлов больше подходят определенные кодировки (это связано с тем, какие языковые символы они могут или не могут обрабатывать), хотя обычно предпочтительной является кодировка Юникод.</span><span class="sxs-lookup"><span data-stu-id="0cb46-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="0cb46-113">Дополнительные сведения см. в статьях [Кодировки файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) и <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="0cb46-113">For more information, see [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="0cb46-114">Неверные пути</span><span class="sxs-lookup"><span data-stu-id="0cb46-114">Incorrect paths</span></span>  
 <span data-ttu-id="0cb46-115">Прописывая пути к файлам (особенно если речь идет об относительных путях), легко ошибиться.</span><span class="sxs-lookup"><span data-stu-id="0cb46-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="0cb46-116">Большинство неполадок можно устранить, просто проверив правильность указанного пути.</span><span class="sxs-lookup"><span data-stu-id="0cb46-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="0cb46-117">Дополнительные сведения см. в разделе [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span><span class="sxs-lookup"><span data-stu-id="0cb46-117">For more information, see [How to: Parse File Paths](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb46-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0cb46-118">See also</span></span>  
 <span data-ttu-id="0cb46-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="0cb46-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="0cb46-120">[Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span><span class="sxs-lookup"><span data-stu-id="0cb46-120">[Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span></span>  
 <span data-ttu-id="0cb46-121">[Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md) </span><span class="sxs-lookup"><span data-stu-id="0cb46-121">[Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md) </span></span>  
 [<span data-ttu-id="0cb46-122">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="0cb46-122">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)

