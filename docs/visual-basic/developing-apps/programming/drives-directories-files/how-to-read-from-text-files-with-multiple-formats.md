---
title: "Практическое руководство. Чтение текстовых файлов различных форматов в Visual Basic"
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
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method, parsing structured text files
- PeekChars method, determining format of text
- reading text files, multiple formats
- I/O [Visual Basic], reading text files
- text files, reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
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
ms.openlocfilehash: be085e5a0f7a57890893ba310db3c66480b300da
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a><span data-ttu-id="21bc8-102">Практическое руководство. Чтение текстовых файлов различных форматов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21bc8-102">How to: Read From Text Files with Multiple Formats in Visual Basic</span></span>
<span data-ttu-id="21bc8-103">Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="21bc8-103">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="21bc8-104">Обработать файл, имеющий содержимое в нескольких форматах, можно с помощью метода `PeekChars`, который позволяет определять формат каждой анализируемой строки на протяжении всего файла.</span><span class="sxs-lookup"><span data-stu-id="21bc8-104">You can process a file with multiple formats by using the `PeekChars` method to determine the format of each line as you parse through the file.</span></span>  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a><span data-ttu-id="21bc8-105">Анализ текстового файла с содержимым в нескольких форматах</span><span class="sxs-lookup"><span data-stu-id="21bc8-105">To parse a text file with multiple formats</span></span>  
  
1.  <span data-ttu-id="21bc8-106">Добавьте текстовый файл с именем testfile.txt в проект.</span><span class="sxs-lookup"><span data-stu-id="21bc8-106">Add a text file named testfile.txt to your project.</span></span> <span data-ttu-id="21bc8-107">Добавьте в текстовый файл следующее содержимое.</span><span class="sxs-lookup"><span data-stu-id="21bc8-107">Add the following content to the text file.</span></span>  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  <span data-ttu-id="21bc8-108">Определите ожидаемый формат и формат, используемый при сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="21bc8-108">Define the expected format and the format used when an error is reported.</span></span> <span data-ttu-id="21bc8-109">Последним элементом в каждом массиве является -1, поэтому предполагается, что ширина последнего поля может изменяться.</span><span class="sxs-lookup"><span data-stu-id="21bc8-109">The last entry in each array is -1, therefore the last field is assumed to be of variable width.</span></span> <span data-ttu-id="21bc8-110">Это происходит, когда последний элемент массива меньше или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="21bc8-110">This occurs when the last entry in the array is less than or equal to 0.</span></span>  
  
     <span data-ttu-id="21bc8-111">[!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="21bc8-111">[!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]</span></span>  
  
3.  <span data-ttu-id="21bc8-112">Создайте объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, определив ширину и формат.</span><span class="sxs-lookup"><span data-stu-id="21bc8-112">Create a new <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object, defining the width and format.</span></span>  
  
     <span data-ttu-id="21bc8-113">[!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="21bc8-113">[!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]</span></span>  
  
4.  <span data-ttu-id="21bc8-114">Переберите в цикле строки, проверяя формат перед чтением.</span><span class="sxs-lookup"><span data-stu-id="21bc8-114">Loop through the rows, testing for format before reading.</span></span>  
  
     <span data-ttu-id="21bc8-115">[!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="21bc8-115">[!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]</span></span>  
  
5.  <span data-ttu-id="21bc8-116">Выведите сообщения об ошибках на консоль.</span><span class="sxs-lookup"><span data-stu-id="21bc8-116">Write errors to the console.</span></span>  
  
     <span data-ttu-id="21bc8-117">[!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="21bc8-117">[!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="21bc8-118">Пример</span><span class="sxs-lookup"><span data-stu-id="21bc8-118">Example</span></span>  
 <span data-ttu-id="21bc8-119">Далее приведен полный пример, считывающий из файла `testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="21bc8-119">Following is the complete example that reads from the file `testfile.txt`.</span></span>  
  
 <span data-ttu-id="21bc8-120">[!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="21bc8-120">[!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="21bc8-121">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="21bc8-121">Robust Programming</span></span>  
 <span data-ttu-id="21bc8-122">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="21bc8-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="21bc8-123">Строка не может быть проанализирована с использованием указанного формата (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="21bc8-123">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="21bc8-124">Сообщение исключения содержит строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> присвоено тексту, который содержится в этой строке.</span><span class="sxs-lookup"><span data-stu-id="21bc8-124">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
-   <span data-ttu-id="21bc8-125">Указанный файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="21bc8-125">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="21bc8-126">Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="21bc8-126">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="21bc8-127">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="21bc8-127">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="21bc8-128">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="21bc8-128">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="21bc8-129">Пользователь не имеет необходимых разрешений для доступа к файлу (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="21bc8-129">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bc8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="21bc8-130">See Also</span></span>  
 <span data-ttu-id="21bc8-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21bc8-131"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName></span></span>   
 <span data-ttu-id="21bc8-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A></span><span class="sxs-lookup"><span data-stu-id="21bc8-132"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A></span></span>   
 <span data-ttu-id="21bc8-133"><xref:Microsoft.VisualBasic.FileIO.MalformedLineException></span><span class="sxs-lookup"><span data-stu-id="21bc8-133"><xref:Microsoft.VisualBasic.FileIO.MalformedLineException></span></span>   
 <span data-ttu-id="21bc8-134"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span><span class="sxs-lookup"><span data-stu-id="21bc8-134"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span></span>   
 <span data-ttu-id="21bc8-135"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A></span><span class="sxs-lookup"><span data-stu-id="21bc8-135"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A></span></span>   
 <span data-ttu-id="21bc8-136"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A></span><span class="sxs-lookup"><span data-stu-id="21bc8-136"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A></span></span>   
 <span data-ttu-id="21bc8-137">[Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="21bc8-137">[How to: Read From Comma-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span></span>  
 <span data-ttu-id="21bc8-138">[Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="21bc8-138">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 [<span data-ttu-id="21bc8-139">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="21bc8-139">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)

