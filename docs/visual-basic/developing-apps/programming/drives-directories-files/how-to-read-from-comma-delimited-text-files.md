---
title: Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: 050f8635e1cb0fa1a2dd29249873e3bf12dad121
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520390"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="1f013-102">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f013-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="1f013-103">Объект `TextFieldParser` позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="1f013-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="1f013-104">Свойство `TextFieldType` определяет, является ли файл файлом с разделителями или с полями фиксированной ширины текста.</span><span class="sxs-lookup"><span data-stu-id="1f013-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="1f013-105">Анализ текстового файла с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="1f013-105">To parse a comma delimited text file</span></span>  
  
1.  <span data-ttu-id="1f013-106">Создайте объект `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="1f013-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="1f013-107">Следующий код создает объект `TextFieldParser` с именем `MyReader` и открывает файл `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="1f013-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     [!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_1.vb)]  
  
2.  <span data-ttu-id="1f013-108">Определение тип `TextField` и разделитель.</span><span class="sxs-lookup"><span data-stu-id="1f013-108">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="1f013-109">Следующий код определяет для свойства `TextFieldType` значение `Delimited`, а для разделителя — ",".</span><span class="sxs-lookup"><span data-stu-id="1f013-109">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     [!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_2.vb)]  
  
3.  <span data-ttu-id="1f013-110">Просмотрите поля в файле.</span><span class="sxs-lookup"><span data-stu-id="1f013-110">Loop through the fields in the file.</span></span> <span data-ttu-id="1f013-111">Если какие-либо строки повреждены, выведите сообщение об ошибке и продолжите анализ.</span><span class="sxs-lookup"><span data-stu-id="1f013-111">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="1f013-112">Следующий код выполняет цикл по файлу, отображая каждое поле по очереди и сообщая обо всех полях с неправильным форматированием.</span><span class="sxs-lookup"><span data-stu-id="1f013-112">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     [!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_3.vb)]  
  
4.  <span data-ttu-id="1f013-113">Закройте блоки `While` и `Using` операторами `End While` и `End Using`.</span><span class="sxs-lookup"><span data-stu-id="1f013-113">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="1f013-114">Пример</span><span class="sxs-lookup"><span data-stu-id="1f013-114">Example</span></span>  
 <span data-ttu-id="1f013-115">В этом примере производится чтение данных из файла `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="1f013-115">This example reads from the file `test.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-delimited-text-files_5.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1f013-116">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="1f013-116">Robust programming</span></span>  
 <span data-ttu-id="1f013-117">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="1f013-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="1f013-118">Строка не может быть проанализирована с использованием указанного формата (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="1f013-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="1f013-119">Сообщение исключения содержит строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> содержит текст, который содержится в этой строке.</span><span class="sxs-lookup"><span data-stu-id="1f013-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
-   <span data-ttu-id="1f013-120">Указанный файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="1f013-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="1f013-121">Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="1f013-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="1f013-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="1f013-122">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="1f013-123">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="1f013-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="1f013-124">У пользователя нет необходимых разрешений для доступа к файлу (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="1f013-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f013-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1f013-125">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="1f013-126">Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="1f013-126">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="1f013-127">Практическое руководство. Чтение из текстовых файлов различных форматов</span><span class="sxs-lookup"><span data-stu-id="1f013-127">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="1f013-128">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="1f013-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="1f013-129">Пошаговое руководство: Операции с файлами и каталогами в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f013-129">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="1f013-130">Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы</span><span class="sxs-lookup"><span data-stu-id="1f013-130">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
