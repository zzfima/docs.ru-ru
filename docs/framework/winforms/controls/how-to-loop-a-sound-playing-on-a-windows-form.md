---
title: Практическое руководство. Циклическое воспроизведение звука в Windows Forms
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
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a88bf4b9dc84af8c6e81167c989943754f64b7d8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="f4c0d-102">Практическое руководство. Циклическое воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4c0d-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="f4c0d-103">В следующем примере кода выполняется повторяющееся воспроизведение звука.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="f4c0d-104">Когда этот код запускается в обработчике события `stopPlayingButton_Click`, воспроизведение звука останавливается.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="f4c0d-105">Если звук не воспроизводится, то ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c0d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f4c0d-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4c0d-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f4c0d-107">Compiling the Code</span></span>  
 <span data-ttu-id="f4c0d-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f4c0d-108">This example requires:</span></span>  
  
-   <span data-ttu-id="f4c0d-109">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="f4c0d-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="f4c0d-110">замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="f4c0d-111">Сведения о построении этого примера из командной строки для visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-111">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f4c0d-112">Можно также построить этот пример, в Visual Studio, вставив код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="f4c0d-113">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f4c0d-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f4c0d-114">Robust Programming</span></span>  
 <span data-ttu-id="f4c0d-115">Операции с файлами должны быть включены в соответствующие блоки обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-115">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="f4c0d-116">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="f4c0d-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f4c0d-117">Недопустимое имя пути</span><span class="sxs-lookup"><span data-stu-id="f4c0d-117">The path name is malformed.</span></span> <span data-ttu-id="f4c0d-118">(например, путь содержит недопустимые символы или состоит только из символ-разделитель (класс <xref:System.ArgumentException>)).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-118">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="f4c0d-119">Путь доступен только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-119">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="f4c0d-120">Имя пути — `Nothing` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-120">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="f4c0d-121">Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-121">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="f4c0d-122">Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-122">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="f4c0d-123">Путь содержит только двоеточие (":") (класс <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="f4c0d-123">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f4c0d-124">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f4c0d-124">.NET Framework Security</span></span>  
 <span data-ttu-id="f4c0d-125">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-125">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="f4c0d-126">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-126">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="f4c0d-127">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="f4c0d-127">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c0d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f4c0d-128">See Also</span></span>  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>  
 [<span data-ttu-id="f4c0d-129">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4c0d-129">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="f4c0d-130">Общие сведения о классе SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="f4c0d-130">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)
