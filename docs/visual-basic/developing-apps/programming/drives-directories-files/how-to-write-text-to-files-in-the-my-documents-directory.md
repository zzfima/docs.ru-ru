---
title: Практическое руководство. Запись текста в файлы в каталоге "Мои документы"
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bc62f2bc63a2ea185b8ea4c8d271dd28d347d6f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334525"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="2af8b-102">Практическое руководство. Запись текста в файлы в каталоге "Мои документы" в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2af8b-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="2af8b-103">Объект `My.Computer.FileSystem.SpecialDirectories` позволяет получить доступ к специальным каталогам, таким как каталог **Мои документы**.</span><span class="sxs-lookup"><span data-stu-id="2af8b-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="2af8b-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="2af8b-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="2af8b-105">Запись новых текстовых файлов в каталог "Мои документы"</span><span class="sxs-lookup"><span data-stu-id="2af8b-105">To write new text files in the My Documents directory</span></span>  
  
1. <span data-ttu-id="2af8b-106">Укажите путь в свойстве `My.Computer.FileSystem.SpecialDirectories.MyDocuments`.</span><span class="sxs-lookup"><span data-stu-id="2af8b-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="2af8b-107">Используйте метод `WriteAllText` для записи текста в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="2af8b-107">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="2af8b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2af8b-108">Example</span></span>  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2af8b-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2af8b-109">Compiling the Code</span></span>  

 <span data-ttu-id="2af8b-110">Замените имя `test.txt` на имя файла, в который требуется выполнить запись.</span><span class="sxs-lookup"><span data-stu-id="2af8b-110">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2af8b-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="2af8b-111">Robust Programming</span></span>  

 <span data-ttu-id="2af8b-112">Этот код возвращает все исключения, которые могут произойти при записи текста в файл.</span><span class="sxs-lookup"><span data-stu-id="2af8b-112">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="2af8b-113">Можно уменьшить вероятность возникновения исключений с помощью элементов управления Windows Forms, таких как компоненты [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) и [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md), которые позволяют пользователям выбирать только допустимые имена файлов.</span><span class="sxs-lookup"><span data-stu-id="2af8b-113">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) and the [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="2af8b-114">Однако использование этих элементов управления не гарантирует полную надежность.</span><span class="sxs-lookup"><span data-stu-id="2af8b-114">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="2af8b-115">В период между моментом выбора пользователем файла и моментом выполнения кода файловая система может измениться.</span><span class="sxs-lookup"><span data-stu-id="2af8b-115">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="2af8b-116">Таким образом, при работе с файлами обработка исключений почти всегда является необходимой.</span><span class="sxs-lookup"><span data-stu-id="2af8b-116">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2af8b-117">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2af8b-117">.NET Framework Security</span></span>  

 <span data-ttu-id="2af8b-118">Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа.</span><span class="sxs-lookup"><span data-stu-id="2af8b-118">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="2af8b-119">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="2af8b-119">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="2af8b-120">В этом примере создается новый файл.</span><span class="sxs-lookup"><span data-stu-id="2af8b-120">This example creates a new file.</span></span> <span data-ttu-id="2af8b-121">Если приложение создает файл, оно должно иметь разрешение на создание файла в соответствующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="2af8b-121">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="2af8b-122">Для задания разрешений используются списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="2af8b-122">Permissions are set using access control lists.</span></span> <span data-ttu-id="2af8b-123">Если файл уже существует, приложению требуется лишь разрешение на запись (с более низким уровнем).</span><span class="sxs-lookup"><span data-stu-id="2af8b-123">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="2af8b-124">Для повышения безопасности рекомендуется по возможности создавать файлы во время развертывания и предоставлять доступ на чтение только к одному файлу, а не доступ к каталогу с разрешением на создание.</span><span class="sxs-lookup"><span data-stu-id="2af8b-124">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="2af8b-125">По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в корневую папку или папку **Program Files**.</span><span class="sxs-lookup"><span data-stu-id="2af8b-125">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="2af8b-126">Дополнительные сведения см. в разделе [Общие сведения о технологии ACL](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2af8b-126">For more information, see [ACL Technology Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af8b-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2af8b-127">See also</span></span>

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
