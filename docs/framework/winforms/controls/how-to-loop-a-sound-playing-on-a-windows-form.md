---
title: "Практическое руководство. Циклическое воспроизведение звука в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "воспроизведение звуков, выполнение цикла"
  - "звуковые циклы"
  - "SoundPlayer - класс, циклическое воспроизведение"
  - "звуки, выполнение цикла"
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Циклическое воспроизведение звука в Windows Forms
В следующем примере кода выполняется повторяющееся воспроизведение звука.  Когда этот код запускается в обработчике события `stopPlayingButton_Click`, воспроизведение звука останавливается.  Если звук не воспроизводится, то ничего не происходит.  
  
## Пример  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms;  
  
-   замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Отказоустойчивость  
 Операции с файлами должны быть включены в соответствующие блоки обработки исключений.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Недопустимое имя пути  \(например, путь содержит недопустимые символы или состоит только из символ\-разделитель \(класс <xref:System.ArgumentException>\)\).  
  
-   Путь доступен только для чтения \(класс <xref:System.IO.IOException>\).  
  
-   Имя пути — `Nothing` \(класс <xref:System.ArgumentNullException>\).  
  
-   Указано слишком длинное имя пути \(класс <xref:System.IO.PathTooLongException>\).  
  
-   Недопустимый путь \(класс <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Путь содержит только двоеточие \(":"\) \(класс <xref:System.NotSupportedException>\).  
  
## Безопасность платформы .NET Framework  
 По имени файла не всегда можно с уверенностью судить о его содержимом.  Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.  Следует проверять все входные данные перед использованием их в приложении.  
  
## См. также  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>   
 [Практическое руководство. Воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [Общие сведения о классе SoundPlayer](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)