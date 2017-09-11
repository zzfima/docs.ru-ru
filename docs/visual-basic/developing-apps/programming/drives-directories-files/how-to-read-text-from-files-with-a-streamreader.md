---
title: "Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic)"
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
- reading files, text
- text, reading from files
- reading text from files
- files, reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
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
ms.openlocfilehash: d895b32b1613462a6c8dedcc19040b5040f936ec
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="93a04-102">Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93a04-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>
<span data-ttu-id="93a04-103">Объект `My.Computer.FileSystem` предоставляет методы для открытия <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="93a04-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="93a04-104">Методы `OpenTextFileWriter` и `OpenTextFileReader` являются дополнительными методами и отображаются в IntelliSense, только если выбрана вкладка **Все**.</span><span class="sxs-lookup"><span data-stu-id="93a04-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="93a04-105">Чтение строки из файла с помощью средства чтения текста</span><span class="sxs-lookup"><span data-stu-id="93a04-105">To read a line from a file with a text reader</span></span>  
  
-   <span data-ttu-id="93a04-106">Используйте `OpenTextFileReader` метод, чтобы открыть <xref:System.IO.TextReader>, указав файл.</span><span class="sxs-lookup"><span data-stu-id="93a04-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="93a04-107">В этом примере открывается файл с именем `testfile.txt`, считывается строка из него и отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="93a04-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     <span data-ttu-id="93a04-108">[!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="93a04-108">[!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="93a04-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="93a04-109">Robust Programming</span></span>  
 <span data-ttu-id="93a04-110">Файл, который считывается, должен быть текстовым файлом.</span><span class="sxs-lookup"><span data-stu-id="93a04-110">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="93a04-111">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="93a04-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="93a04-112">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="93a04-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="93a04-113">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="93a04-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="93a04-114">Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.</span><span class="sxs-lookup"><span data-stu-id="93a04-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="93a04-115">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="93a04-115">.NET Framework Security</span></span>  
 <span data-ttu-id="93a04-116">Для чтения из файла сборке требуется уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="93a04-116">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="93a04-117">Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа.</span><span class="sxs-lookup"><span data-stu-id="93a04-117">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="93a04-118">Дополнительные сведения см. в разделе [Основы управления доступом для кода](https://msdn.microsoft.com/library/33tceax8).</span><span class="sxs-lookup"><span data-stu-id="93a04-118">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span> <span data-ttu-id="93a04-119">Пользователь также должен иметь доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="93a04-119">The user also needs access to the file.</span></span> <span data-ttu-id="93a04-120">Дополнительные сведения см. в разделе [Общие сведения о технологии ACL](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="93a04-120">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a04-121">См. также</span><span class="sxs-lookup"><span data-stu-id="93a04-121">See Also</span></span>  
 <span data-ttu-id="93a04-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="93a04-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="93a04-123"><xref:System.Windows.Forms.OpenFileDialog></span><span class="sxs-lookup"><span data-stu-id="93a04-123"><xref:System.Windows.Forms.OpenFileDialog></span></span>   
 <span data-ttu-id="93a04-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="93a04-124"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="93a04-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A></span><span class="sxs-lookup"><span data-stu-id="93a04-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A></span></span>   
 <span data-ttu-id="93a04-126">[Компонент SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) </span><span class="sxs-lookup"><span data-stu-id="93a04-126">[SaveFileDialog Component](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) </span></span>  
 [<span data-ttu-id="93a04-127">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="93a04-127">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)

