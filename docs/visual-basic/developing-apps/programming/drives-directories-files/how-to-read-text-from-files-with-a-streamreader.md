---
title: Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 28ef741398b6d8c5cbbdcc3906b4845e6a2a0d86
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486965"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="79196-102">Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79196-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>
<span data-ttu-id="79196-103">Объект `My.Computer.FileSystem` предоставляет методы для открытия <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="79196-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="79196-104">Методы `OpenTextFileWriter` и `OpenTextFileReader` являются дополнительными методами и отображаются в IntelliSense, только если выбрана вкладка **Все**.</span><span class="sxs-lookup"><span data-stu-id="79196-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="79196-105">Чтение строки из файла с помощью средства чтения текста</span><span class="sxs-lookup"><span data-stu-id="79196-105">To read a line from a file with a text reader</span></span>  
  
-   <span data-ttu-id="79196-106">Используйте `OpenTextFileReader` метод, чтобы открыть <xref:System.IO.TextReader>, указав файл.</span><span class="sxs-lookup"><span data-stu-id="79196-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="79196-107">В этом примере открывается файл с именем `testfile.txt`, считывается строка из него и отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="79196-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="79196-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="79196-108">Robust Programming</span></span>  
 <span data-ttu-id="79196-109">Файл, который считывается, должен быть текстовым файлом.</span><span class="sxs-lookup"><span data-stu-id="79196-109">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="79196-110">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="79196-110">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="79196-111">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="79196-111">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="79196-112">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="79196-112">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="79196-113">Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.</span><span class="sxs-lookup"><span data-stu-id="79196-113">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="79196-114">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="79196-114">.NET Framework Security</span></span>  
 <span data-ttu-id="79196-115">Для чтения из файла сборке требуется уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="79196-115">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="79196-116">Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа.</span><span class="sxs-lookup"><span data-stu-id="79196-116">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="79196-117">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="79196-117">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span> <span data-ttu-id="79196-118">Пользователь также должен иметь доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="79196-118">The user also needs access to the file.</span></span> <span data-ttu-id="79196-119">Дополнительные сведения см. в разделе [Общие сведения о технологии ACL](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="79196-119">For more information, see [ACL Technology Overview](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79196-120">См. также</span><span class="sxs-lookup"><span data-stu-id="79196-120">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>  
 [<span data-ttu-id="79196-121">Компонент SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="79196-121">SaveFileDialog Component</span></span>](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)  
 [<span data-ttu-id="79196-122">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="79196-122">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
