---
title: Воспроизведение звуков
ms.date: 07/20/2015
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
ms.openlocfilehash: 416fedd011ff35d2b32d1b64932e3908a73ed14e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345526"
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="748c2-102">Воспроизведение звуков (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="748c2-102">Playing Sounds (Visual Basic)</span></span>

<span data-ttu-id="748c2-103">Объект `My.Computer.Audio` предоставляет методы для воспроизведения звуков.</span><span class="sxs-lookup"><span data-stu-id="748c2-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="748c2-104">Воспроизведение звуков</span><span class="sxs-lookup"><span data-stu-id="748c2-104">Playing Sounds</span></span>  

 <span data-ttu-id="748c2-105">Воспроизведение в фоновом режиме позволяет приложению выполнять другой код во время воспроизведения звуков.</span><span class="sxs-lookup"><span data-stu-id="748c2-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="748c2-106">Метод `My.Computer.Audio.Play` позволяет приложению воспроизводить только один фоновый звук за раз; когда приложение воспроизводит новый фоновый звук, оно останавливает воспроизведение предыдущего фонового звука.</span><span class="sxs-lookup"><span data-stu-id="748c2-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="748c2-107">Вы также можете воспроизвести звук и дождаться его окончания.</span><span class="sxs-lookup"><span data-stu-id="748c2-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="748c2-108">В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук.</span><span class="sxs-lookup"><span data-stu-id="748c2-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="748c2-109">Если `AudioPlayMode.WaitToComplete` указан, `My.Computer.Audio.Play` дожидается завершения звука, прежде чем выполнение вызывающего кода будет продолжено.</span><span class="sxs-lookup"><span data-stu-id="748c2-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="748c2-110">Пользуясь этим примером, убедитесь в том, что имя файла ссылается на звуковой WAV-файл на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="748c2-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 <span data-ttu-id="748c2-111">В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук.</span><span class="sxs-lookup"><span data-stu-id="748c2-111">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="748c2-112">Пользуясь этим примером, убедитесь в том, что ресурсы приложения включают звуковой WAV-файла с именем Waterfall.</span><span class="sxs-lookup"><span data-stu-id="748c2-112">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="748c2-113">Циклическое воспроизведение звука</span><span class="sxs-lookup"><span data-stu-id="748c2-113">Playing Looping Sounds</span></span>  

 <span data-ttu-id="748c2-114">В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме, если задан параметр `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="748c2-114">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="748c2-115">Пользуясь этим примером, убедитесь в том, что имя файла ссылается на звуковой WAV-файл на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="748c2-115">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 <span data-ttu-id="748c2-116">В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме, если задан параметр `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="748c2-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="748c2-117">Пользуясь этим примером, убедитесь в том, что ресурсы приложения включают звуковой WAV-файла с именем Waterfall.</span><span class="sxs-lookup"><span data-stu-id="748c2-117">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 <span data-ttu-id="748c2-118">Код в приведенном выше примере также доступен как фрагмент кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="748c2-118">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="748c2-119">В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Звук**.</span><span class="sxs-lookup"><span data-stu-id="748c2-119">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="748c2-120">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="748c2-120">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="748c2-121">Обычно циклическое воспроизведение звука в приложении в конечном итоге должно прекратиться.</span><span class="sxs-lookup"><span data-stu-id="748c2-121">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="748c2-122">Остановка воспроизведения звуков в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="748c2-122">Stopping the Playing of Sounds in the Background</span></span>  

 <span data-ttu-id="748c2-123">Метод `My.Computer.Audio.Stop` позволяет остановить звук, который воспроизводится в приложении в фоновом режиме или циклически.</span><span class="sxs-lookup"><span data-stu-id="748c2-123">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="748c2-124">Обычно циклическое воспроизведение звука в приложении в какой-то момент должно быть остановлено.</span><span class="sxs-lookup"><span data-stu-id="748c2-124">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="748c2-125">Код в следующем примере останавливает звук, который воспроизводится в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="748c2-125">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 <span data-ttu-id="748c2-126">Код в приведенном выше примере также доступен как фрагмент кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="748c2-126">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="748c2-127">В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Звук**.</span><span class="sxs-lookup"><span data-stu-id="748c2-127">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="748c2-128">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="748c2-128">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="748c2-129">Воспроизведение системных звуков</span><span class="sxs-lookup"><span data-stu-id="748c2-129">Playing System Sounds</span></span>  

 <span data-ttu-id="748c2-130">Метод `My.Computer.Audio.PlaySystemSound` позволяет воспроизвести указанный системный звук.</span><span class="sxs-lookup"><span data-stu-id="748c2-130">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="748c2-131">Метод `My.Computer.Audio.PlaySystemSound` принимает в качестве параметра один из общих членов класса <xref:System.Media.SystemSound>.</span><span class="sxs-lookup"><span data-stu-id="748c2-131">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="748c2-132">Системный звук <xref:System.Media.SystemSounds.Asterisk%2A> обычно обозначает ошибку.</span><span class="sxs-lookup"><span data-stu-id="748c2-132">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="748c2-133">Код в следующем примере использует метод `My.Computer.Audio.PlaySystemSound` для воспроизведения системного звука.</span><span class="sxs-lookup"><span data-stu-id="748c2-133">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="748c2-134">См. также</span><span class="sxs-lookup"><span data-stu-id="748c2-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
