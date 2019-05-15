---
title: Практическое руководство. Чтение текстовых файлов различных форматов в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method [Visual Basic], parsing structured text files
- PeekChars method [Visual Basic], determining format of text
- reading text files [Visual Basic], multiple formats
- I/O [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
ms.openlocfilehash: 9fa484f0a74d900bd6f0365f2ce71fd32e1422db
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623180"
---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a><span data-ttu-id="35106-102">Практическое руководство. Чтение текстовых файлов различных форматов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35106-102">How to: Read From Text Files with Multiple Formats in Visual Basic</span></span>
<span data-ttu-id="35106-103">Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="35106-103">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="35106-104">Обработать файл, имеющий содержимое в нескольких форматах, можно с помощью метода `PeekChars`, который позволяет определять формат каждой анализируемой строки на протяжении всего файла.</span><span class="sxs-lookup"><span data-stu-id="35106-104">You can process a file with multiple formats by using the `PeekChars` method to determine the format of each line as you parse through the file.</span></span>  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a><span data-ttu-id="35106-105">Анализ текстового файла с содержимым в нескольких форматах</span><span class="sxs-lookup"><span data-stu-id="35106-105">To parse a text file with multiple formats</span></span>  
  
1. <span data-ttu-id="35106-106">Добавьте текстовый файл с именем testfile.txt в проект.</span><span class="sxs-lookup"><span data-stu-id="35106-106">Add a text file named testfile.txt to your project.</span></span> <span data-ttu-id="35106-107">Добавьте в текстовый файл следующее содержимое.</span><span class="sxs-lookup"><span data-stu-id="35106-107">Add the following content to the text file.</span></span>  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2. <span data-ttu-id="35106-108">Определите ожидаемый формат и формат, используемый при сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="35106-108">Define the expected format and the format used when an error is reported.</span></span> <span data-ttu-id="35106-109">Последним элементом в каждом массиве является -1, поэтому предполагается, что ширина последнего поля может изменяться.</span><span class="sxs-lookup"><span data-stu-id="35106-109">The last entry in each array is -1, therefore the last field is assumed to be of variable width.</span></span> <span data-ttu-id="35106-110">Это происходит, когда последний элемент массива меньше или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="35106-110">This occurs when the last entry in the array is less than or equal to 0.</span></span>  
  
     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]  
  
3. <span data-ttu-id="35106-111">Создайте объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, определив ширину и формат.</span><span class="sxs-lookup"><span data-stu-id="35106-111">Create a new <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object, defining the width and format.</span></span>  
  
     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]  
  
4. <span data-ttu-id="35106-112">Переберите в цикле строки, проверяя формат перед чтением.</span><span class="sxs-lookup"><span data-stu-id="35106-112">Loop through the rows, testing for format before reading.</span></span>  
  
     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]  
  
5. <span data-ttu-id="35106-113">Выведите сообщения об ошибках на консоль.</span><span class="sxs-lookup"><span data-stu-id="35106-113">Write errors to the console.</span></span>  
  
     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="35106-114">Пример</span><span class="sxs-lookup"><span data-stu-id="35106-114">Example</span></span>  
 <span data-ttu-id="35106-115">Далее приведен полный пример, считывающий из файла `testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="35106-115">Following is the complete example that reads from the file `testfile.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="35106-116">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="35106-116">Robust Programming</span></span>  
 <span data-ttu-id="35106-117">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="35106-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="35106-118">Строка не может быть проанализирована с использованием указанного формата (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="35106-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="35106-119">Сообщение исключения содержит строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> присвоено тексту, который содержится в этой строке.</span><span class="sxs-lookup"><span data-stu-id="35106-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="35106-120">Указанный файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="35106-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="35106-121">Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="35106-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="35106-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="35106-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="35106-123">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="35106-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="35106-124">У пользователя нет необходимых разрешений для доступа к файлу (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="35106-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35106-125">См. также</span><span class="sxs-lookup"><span data-stu-id="35106-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [<span data-ttu-id="35106-126">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="35106-126">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="35106-127">Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="35106-127">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="35106-128">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="35106-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
