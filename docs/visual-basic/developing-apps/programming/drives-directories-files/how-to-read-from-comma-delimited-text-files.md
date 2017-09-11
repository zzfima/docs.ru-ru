---
title: "Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic"
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
- files, parsing
- text files, tasks
- reading text files, comma-delimited
- text files, reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
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
ms.openlocfilehash: 2ae6a3f315a8e433386319d1aa1a7f48726a19bb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="55cd5-102">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55cd5-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="55cd5-103">Объект `TextFieldParser` позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="55cd5-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="55cd5-104">Свойство `TextFieldType` определяет, является ли файл файлом с разделителями или с полями фиксированной ширины текста.</span><span class="sxs-lookup"><span data-stu-id="55cd5-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="55cd5-105">Анализ текстового файла с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="55cd5-105">To parse a comma delimited text file</span></span>  
  
1.  <span data-ttu-id="55cd5-106">Создайте объект `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="55cd5-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="55cd5-107">Следующий код создает объект `TextFieldParser` с именем `MyReader` и открывает файл `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="55cd5-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     <span data-ttu-id="55cd5-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="55cd5-108">[!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]</span></span>  
  
2.  <span data-ttu-id="55cd5-109">Определение тип `TextField` и разделитель.</span><span class="sxs-lookup"><span data-stu-id="55cd5-109">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="55cd5-110">Следующий код определяет для свойства `TextFieldType` значение `Delimited`, а для разделителя — ",".</span><span class="sxs-lookup"><span data-stu-id="55cd5-110">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     <span data-ttu-id="55cd5-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="55cd5-111">[!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]</span></span>  
  
3.  <span data-ttu-id="55cd5-112">Просмотрите поля в файле.</span><span class="sxs-lookup"><span data-stu-id="55cd5-112">Loop through the fields in the file.</span></span> <span data-ttu-id="55cd5-113">Если какие-либо строки повреждены, выведите сообщение об ошибке и продолжите анализ.</span><span class="sxs-lookup"><span data-stu-id="55cd5-113">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="55cd5-114">Следующий код выполняет цикл по файлу, отображая каждое поле по очереди и сообщая обо всех полях с неправильным форматированием.</span><span class="sxs-lookup"><span data-stu-id="55cd5-114">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     <span data-ttu-id="55cd5-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="55cd5-115">[!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]</span></span>  
  
4.  <span data-ttu-id="55cd5-116">Закройте блоки `While` и `Using` операторами `End While` и `End Using`.</span><span class="sxs-lookup"><span data-stu-id="55cd5-116">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     <span data-ttu-id="55cd5-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="55cd5-117">[!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="55cd5-118">Пример</span><span class="sxs-lookup"><span data-stu-id="55cd5-118">Example</span></span>  
 <span data-ttu-id="55cd5-119">В этом примере производится чтение данных из файла `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="55cd5-119">This example reads from the file `test.txt`.</span></span>  
  
 <span data-ttu-id="55cd5-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="55cd5-120">[!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="55cd5-121">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="55cd5-121">Robust programming</span></span>  
 <span data-ttu-id="55cd5-122">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="55cd5-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="55cd5-123">Строка не может быть проанализирована с использованием указанного формата (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="55cd5-123">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="55cd5-124">Сообщение исключения содержит строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> содержит текст, который содержится в этой строке.</span><span class="sxs-lookup"><span data-stu-id="55cd5-124">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
-   <span data-ttu-id="55cd5-125">Указанный файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="55cd5-125">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="55cd5-126">Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="55cd5-126">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="55cd5-127">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="55cd5-127">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="55cd5-128">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="55cd5-128">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="55cd5-129">У пользователя нет необходимых разрешений для доступа к файлу (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="55cd5-129">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cd5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="55cd5-130">See also</span></span>  
 <span data-ttu-id="55cd5-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="55cd5-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="55cd5-132">[Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="55cd5-132">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 <span data-ttu-id="55cd5-133">[Практическое руководство. Чтение из текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="55cd5-133">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="55cd5-134">[Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span><span class="sxs-lookup"><span data-stu-id="55cd5-134">[Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md) </span></span>  
 <span data-ttu-id="55cd5-135">[Пошаговое руководство. Операции с файлами и каталогами в Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="55cd5-135">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="55cd5-136">Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы</span><span class="sxs-lookup"><span data-stu-id="55cd5-136">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)

