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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345526"
---
# <a name="playing-sounds-visual-basic"></a>Воспроизведение звуков (Visual Basic)

Объект `My.Computer.Audio` предоставляет методы для воспроизведения звуков.  
  
## <a name="playing-sounds"></a>Воспроизведение звуков  

 Воспроизведение в фоновом режиме позволяет приложению выполнять другой код во время воспроизведения звуков. Метод `My.Computer.Audio.Play` позволяет приложению воспроизводить только один фоновый звук за раз; когда приложение воспроизводит новый фоновый звук, оно останавливает воспроизведение предыдущего фонового звука. Вы также можете воспроизвести звук и дождаться его окончания.  
  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук. Если `AudioPlayMode.WaitToComplete` указан, `My.Computer.Audio.Play` дожидается завершения звука, прежде чем выполнение вызывающего кода будет продолжено. Пользуясь этим примером, убедитесь в том, что имя файла ссылается на звуковой WAV-файл на вашем компьютере.  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит звук. Пользуясь этим примером, убедитесь в том, что ресурсы приложения включают звуковой WAV-файла с именем Waterfall.  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a>Циклическое воспроизведение звука  

 В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме, если задан параметр `PlayMode.BackgroundLoop`. Пользуясь этим примером, убедитесь в том, что имя файла ссылается на звуковой WAV-файл на вашем компьютере.  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 В следующем примере метод `My.Computer.Audio.Play` воспроизводит заданный звук в фоновом режиме, если задан параметр `PlayMode.BackgroundLoop`. Пользуясь этим примером, убедитесь в том, что ресурсы приложения включают звуковой WAV-файла с именем Waterfall.  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 Код в приведенном выше примере также доступен как фрагмент кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Звук**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
 Обычно циклическое воспроизведение звука в приложении в конечном итоге должно прекратиться.  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a>Остановка воспроизведения звуков в фоновом режиме  

 Метод `My.Computer.Audio.Stop` позволяет остановить звук, который воспроизводится в приложении в фоновом режиме или циклически.  
  
 Обычно циклическое воспроизведение звука в приложении в какой-то момент должно быть остановлено.  
  
 Код в следующем примере останавливает звук, который воспроизводится в фоновом режиме.  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 Код в приведенном выше примере также доступен как фрагмент кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Звук**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="playing-system-sounds"></a>Воспроизведение системных звуков  

 Метод `My.Computer.Audio.PlaySystemSound` позволяет воспроизвести указанный системный звук.  
  
 Метод `My.Computer.Audio.PlaySystemSound` принимает в качестве параметра один из общих членов класса <xref:System.Media.SystemSound>. Системный звук <xref:System.Media.SystemSounds.Asterisk%2A> обычно обозначает ошибку.  
  
 Код в следующем примере использует метод `My.Computer.Audio.PlaySystemSound` для воспроизведения системного звука.  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
