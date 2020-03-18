---
title: Практическое руководство. Чтение текста из файлов с помощью StreamReader
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 572463d1f03d768fb133f2dac59b012051f053bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334566"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="94459-102">Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94459-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>

<span data-ttu-id="94459-103">Объект `My.Computer.FileSystem` предоставляет методы для открытия <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="94459-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="94459-104">Методы `OpenTextFileWriter` и `OpenTextFileReader` являются дополнительными методами и отображаются в IntelliSense, только если выбрана вкладка **Все**.</span><span class="sxs-lookup"><span data-stu-id="94459-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="94459-105">Чтение строки из файла с помощью средства чтения текста</span><span class="sxs-lookup"><span data-stu-id="94459-105">To read a line from a file with a text reader</span></span>  
  
- <span data-ttu-id="94459-106">Используйте `OpenTextFileReader` метод, чтобы открыть <xref:System.IO.TextReader>, указав файл.</span><span class="sxs-lookup"><span data-stu-id="94459-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="94459-107">В этом примере открывается файл с именем `testfile.txt`, считывается строка из него и отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="94459-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     [!code-vb[VbFileIORead#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="94459-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="94459-108">Robust Programming</span></span>  

 <span data-ttu-id="94459-109">Файл, который считывается, должен быть текстовым файлом.</span><span class="sxs-lookup"><span data-stu-id="94459-109">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="94459-110">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="94459-110">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="94459-111">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="94459-111">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="94459-112">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="94459-112">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="94459-113">Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.</span><span class="sxs-lookup"><span data-stu-id="94459-113">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="94459-114">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="94459-114">.NET Framework Security</span></span>  

 <span data-ttu-id="94459-115">Для чтения из файла сборке требуется уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="94459-115">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="94459-116">Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа.</span><span class="sxs-lookup"><span data-stu-id="94459-116">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="94459-117">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="94459-117">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span> <span data-ttu-id="94459-118">Пользователь также должен иметь доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="94459-118">The user also needs access to the file.</span></span> <span data-ttu-id="94459-119">Дополнительные сведения см. в разделе [Общие сведения о технологии ACL](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="94459-119">For more information, see [ACL Technology Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94459-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94459-120">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [<span data-ttu-id="94459-121">Компонент SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="94459-121">SaveFileDialog Component</span></span>](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [<span data-ttu-id="94459-122">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="94459-122">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
