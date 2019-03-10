---
title: Практическое руководство. Цикл звуков в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: 43fcc472960cc3f2432d3872160d9ace4c617836
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719277"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="50f2d-102">Практическое руководство. Цикл звуков в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50f2d-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="50f2d-103">В следующем примере кода выполняется повторяющееся воспроизведение звука.</span><span class="sxs-lookup"><span data-stu-id="50f2d-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="50f2d-104">Когда этот код запускается в обработчике события `stopPlayingButton_Click`, воспроизведение звука останавливается.</span><span class="sxs-lookup"><span data-stu-id="50f2d-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="50f2d-105">Если звук не воспроизводится, то ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="50f2d-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50f2d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="50f2d-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50f2d-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="50f2d-107">Compiling the Code</span></span>  
 <span data-ttu-id="50f2d-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="50f2d-108">This example requires:</span></span>  
  
-   <span data-ttu-id="50f2d-109">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="50f2d-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="50f2d-110">замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="50f2d-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="50f2d-111">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="50f2d-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="50f2d-112">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="50f2d-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="50f2d-113">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="50f2d-113">Robust Programming</span></span>  
 <span data-ttu-id="50f2d-114">Операции с файлами должны быть включены в соответствующие блоки обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="50f2d-114">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="50f2d-115">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="50f2d-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="50f2d-116">Недопустимое имя пути</span><span class="sxs-lookup"><span data-stu-id="50f2d-116">The path name is malformed.</span></span> <span data-ttu-id="50f2d-117">(например, путь содержит недопустимые символы или состоит только из символ-разделитель (класс <xref:System.ArgumentException>)).</span><span class="sxs-lookup"><span data-stu-id="50f2d-117">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="50f2d-118">Путь доступен только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="50f2d-118">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="50f2d-119">Имя пути — `Nothing` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="50f2d-119">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="50f2d-120">Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="50f2d-120">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="50f2d-121">Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="50f2d-121">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="50f2d-122">Путь содержит только двоеточие (":") (класс <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="50f2d-122">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="50f2d-123">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="50f2d-123">.NET Framework Security</span></span>  
 <span data-ttu-id="50f2d-124">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="50f2d-124">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="50f2d-125">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="50f2d-125">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="50f2d-126">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="50f2d-126">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f2d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="50f2d-127">See also</span></span>
- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="50f2d-128">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50f2d-128">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="50f2d-129">Общие сведения о классе SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="50f2d-129">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
