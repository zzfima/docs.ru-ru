---
title: "Воспроизведение звуков (Visual Basic)"
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
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
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
ms.openlocfilehash: a15efff54bd54fdaced6c741cd6acf5c8b544cdd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="e8d29-102">Воспроизведение звуков (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8d29-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="e8d29-103">Объект `My.Computer.Audio` предоставляет методы для воспроизведения звуков.</span><span class="sxs-lookup"><span data-stu-id="e8d29-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="e8d29-104">Воспроизведение звуков</span><span class="sxs-lookup"><span data-stu-id="e8d29-104">Playing Sounds</span></span>  
 <span data-ttu-id="e8d29-105">Воспроизведение в фоновом режиме позволяет приложению выполнять другой код во время воспроизведения звуков.</span><span class="sxs-lookup"><span data-stu-id="e8d29-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="e8d29-106">Метод `My.Computer.Audio.Play` позволяет приложению воспроизводить только один фоновый звук за раз; когда приложение воспроизводит новый фоновый звук, оно останавливает воспроизведение предыдущего фонового звука.</span><span class="sxs-lookup"><span data-stu-id="e8d29-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="e8d29-107">Вы также можете воспроизвести звук и дождаться его окончания.</span><span class="sxs-lookup"><span data-stu-id="e8d29-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="e8d29-108">В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук.</span><span class="sxs-lookup"><span data-stu-id="e8d29-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="e8d29-109">Если `AudioPlayMode.WaitToComplete` указан, `My.Computer.Audio.Play` дожидается завершения звука, прежде чем выполнение вызывающего кода будет продолжено.</span><span class="sxs-lookup"><span data-stu-id="e8d29-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="e8d29-110">Пользуясь этим примером, убедитесь в том, что имя файла ссылается на звуковой WAV-файл на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8d29-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 <span data-ttu-id="e8d29-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8d29-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span></span>  
  
 <span data-ttu-id="e8d29-112">В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук.</span><span class="sxs-lookup"><span data-stu-id="e8d29-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="e8d29-113">Пользуясь этим примером, убедитесь в том, что ресурсы приложения включают звуковой WAV-файла с именем Waterfall.</span><span class="sxs-lookup"><span data-stu-id="e8d29-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="e8d29-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8d29-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span></span>  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="e8d29-115">Циклическое воспроизведение звука</span><span class="sxs-lookup"><span data-stu-id="e8d29-115">Playing Looping Sounds</span></span>  
 <span data-ttu-id="e8d29-116">В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме, если задан параметр `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="e8d29-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="e8d29-117">Пользуясь этим примером, убедитесь в том, что имя файла ссылается на звуковой WAV-файл на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8d29-117">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 <span data-ttu-id="e8d29-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8d29-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span></span>  
  
 <span data-ttu-id="e8d29-119">В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме, если задан параметр `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="e8d29-119">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="e8d29-120">Пользуясь этим примером, убедитесь в том, что ресурсы приложения включают звуковой WAV-файла с именем Waterfall.</span><span class="sxs-lookup"><span data-stu-id="e8d29-120">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="e8d29-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8d29-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span></span>  
  
 <span data-ttu-id="e8d29-122">Код в приведенном выше примере также доступен как фрагмент кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e8d29-122">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e8d29-123">В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Звук**.</span><span class="sxs-lookup"><span data-stu-id="e8d29-123">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="e8d29-124">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="e8d29-124">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="e8d29-125">Обычно циклическое воспроизведение звука в приложении в конечном итоге должно прекратиться.</span><span class="sxs-lookup"><span data-stu-id="e8d29-125">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="e8d29-126">Остановка воспроизведения звуков в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="e8d29-126">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="e8d29-127">Метод `My.Computer.Audio.Stop` позволяет остановить звук, который воспроизводится в приложении в фоновом режиме или циклически.</span><span class="sxs-lookup"><span data-stu-id="e8d29-127">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="e8d29-128">Обычно циклическое воспроизведение звука в приложении в какой-то момент должно быть остановлено.</span><span class="sxs-lookup"><span data-stu-id="e8d29-128">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="e8d29-129">Код в следующем примере останавливает звук, который воспроизводится в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="e8d29-129">The following example stops a sound that is playing in the background.</span></span>  
  
 <span data-ttu-id="e8d29-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8d29-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span></span>  
  
 <span data-ttu-id="e8d29-131">Код в приведенном выше примере также доступен как фрагмент кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e8d29-131">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e8d29-132">В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Звук**.</span><span class="sxs-lookup"><span data-stu-id="e8d29-132">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="e8d29-133">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="e8d29-133">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="e8d29-134">Воспроизведение системных звуков</span><span class="sxs-lookup"><span data-stu-id="e8d29-134">Playing System Sounds</span></span>  
 <span data-ttu-id="e8d29-135">Метод `My.Computer.Audio.PlaySystemSound` позволяет воспроизвести указанный системный звук.</span><span class="sxs-lookup"><span data-stu-id="e8d29-135">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="e8d29-136">Метод `My.Computer.Audio.PlaySystemSound` принимает в качестве параметра один из общих членов класса <xref:System.Media.SystemSound>.</span><span class="sxs-lookup"><span data-stu-id="e8d29-136">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="e8d29-137">Системный звук <xref:System.Media.SystemSounds.Asterisk%2A> обычно обозначает ошибку.</span><span class="sxs-lookup"><span data-stu-id="e8d29-137">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="e8d29-138">Код в следующем примере использует метод `My.Computer.Audio.PlaySystemSound` для воспроизведения системного звука.</span><span class="sxs-lookup"><span data-stu-id="e8d29-138">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 <span data-ttu-id="e8d29-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8d29-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d29-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e8d29-140">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>

