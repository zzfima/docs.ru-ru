---
title: Практическое руководство. Асинхронная загрузка звука в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3fb21216f75f90b6333b6448a2be74843eb1c672
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="00fe9-102">Практическое руководство. Асинхронная загрузка звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00fe9-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="00fe9-103">В примере кода ниже производится асинхронная загрузка звука по URL-адресу, после чего он воспроизводится в новом потоке.</span><span class="sxs-lookup"><span data-stu-id="00fe9-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00fe9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="00fe9-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00fe9-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="00fe9-105">Compiling the Code</span></span>  
 <span data-ttu-id="00fe9-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="00fe9-106">This example requires:</span></span>  
  
-   <span data-ttu-id="00fe9-107">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="00fe9-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="00fe9-108">замена имени файла `"http://www.tailspintoys.com/sounds/stop.wav"` на допустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="00fe9-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="00fe9-109">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="00fe9-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="00fe9-110">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="00fe9-110">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="00fe9-111">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="00fe9-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="00fe9-112">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="00fe9-112">Robust Programming</span></span>  
 <span data-ttu-id="00fe9-113">Операции с файлами должны быть включены в соответствующие блоки обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="00fe9-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="00fe9-114">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="00fe9-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="00fe9-115">Недопустимое имя пути</span><span class="sxs-lookup"><span data-stu-id="00fe9-115">The path name is malformed.</span></span> <span data-ttu-id="00fe9-116">(например, путь содержит недопустимые символы или состоит только из пробелов (класс <xref:System.ArgumentException>)).</span><span class="sxs-lookup"><span data-stu-id="00fe9-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="00fe9-117">Путь доступен только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="00fe9-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="00fe9-118">Имя пути — `Nothing` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="00fe9-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="00fe9-119">Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="00fe9-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="00fe9-120">Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="00fe9-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="00fe9-121">Путь содержит только двоеточие (":") (класс <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="00fe9-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="00fe9-122">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="00fe9-122">.NET Framework Security</span></span>  
 <span data-ttu-id="00fe9-123">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="00fe9-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="00fe9-124">Например, файл с именем `Form1.vb` может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="00fe9-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="00fe9-125">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="00fe9-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00fe9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="00fe9-126">See Also</span></span>  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <xref:System.Media.SoundPlayer.LoadCompleted>  
 <xref:System.Media.SoundPlayer.Play%2A>  
 [<span data-ttu-id="00fe9-127">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00fe9-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
