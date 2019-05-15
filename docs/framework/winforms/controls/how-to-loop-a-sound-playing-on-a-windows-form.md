---
title: Практическое руководство. Циклическое воспроизведение звука в Windows Forms
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
ms.openlocfilehash: e14d9de2326234b86c1f24b227e86f822fbfdb71
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592359"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="c444c-102">Практическое руководство. Циклическое воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c444c-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="c444c-103">В следующем примере кода выполняется повторяющееся воспроизведение звука.</span><span class="sxs-lookup"><span data-stu-id="c444c-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="c444c-104">Когда этот код запускается в обработчике события `stopPlayingButton_Click`, воспроизведение звука останавливается.</span><span class="sxs-lookup"><span data-stu-id="c444c-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="c444c-105">Если звук не воспроизводится, то ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="c444c-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c444c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="c444c-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c444c-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c444c-107">Compiling the Code</span></span>  
 <span data-ttu-id="c444c-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c444c-108">This example requires:</span></span>  
  
- <span data-ttu-id="c444c-109">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="c444c-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="c444c-110">замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="c444c-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c444c-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="c444c-111">Robust Programming</span></span>  
 <span data-ttu-id="c444c-112">Операции с файлами должны быть включены в соответствующие блоки обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="c444c-112">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="c444c-113">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="c444c-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c444c-114">Недопустимое имя пути</span><span class="sxs-lookup"><span data-stu-id="c444c-114">The path name is malformed.</span></span> <span data-ttu-id="c444c-115">(например, путь содержит недопустимые символы или состоит только из символ-разделитель (класс <xref:System.ArgumentException>)).</span><span class="sxs-lookup"><span data-stu-id="c444c-115">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="c444c-116">Путь доступен только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c444c-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="c444c-117">Имя пути — `Nothing` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c444c-117">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="c444c-118">Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="c444c-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="c444c-119">Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="c444c-119">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="c444c-120">Путь содержит только двоеточие (":") (класс <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="c444c-120">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c444c-121">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c444c-121">.NET Framework Security</span></span>  
 <span data-ttu-id="c444c-122">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="c444c-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="c444c-123">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c444c-123">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="c444c-124">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="c444c-124">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c444c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c444c-125">See also</span></span>

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="c444c-126">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c444c-126">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="c444c-127">Общие сведения о классе SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="c444c-127">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
