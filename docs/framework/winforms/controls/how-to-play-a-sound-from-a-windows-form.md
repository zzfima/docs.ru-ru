---
title: "Практическое руководство. Воспроизведение звука в Windows Forms | Microsoft Docs"
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
  - "воспроизведение звуков в Windows Forms"
  - "воспроизведение звуков"
  - "SoundPlayer - класс"
  - "звуки"
  - "Объект My.Computer.Audio, воспроизведение звуков"
  - "примеры [Windows Forms] звуков"
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Воспроизведение звука в Windows Forms
В этом примере воспроизводится звук по заданному пути во время выполнения.  
  
## <a name="example"></a>Пример  
  
```vb  
Sub PlaySimpleSound()  
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")  
End Sub  
```  
  
```csharp  
private void playSimpleSound()  
{  
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");  
    simpleSound.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.  
  
-   (C#) Ссылку на <xref:System.Media?displayProperty=fullName> пространства имен.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Файл операции должны быть включены в соответствующие структурированные блоки обработки исключений.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Недопустимое имя пути Например, оно содержит недопустимые символы или только пробелы (<xref:System.ArgumentException> класса).  
  
-   Путь доступен только для чтения (<xref:System.IO.IOException> класса).  
  
-   Недопустимое имя пути `null` (<xref:System.ArgumentNullException> класса).  
  
-   Указано слишком длинное имя пути (<xref:System.IO.PathTooLongException> класса).  
  
-   Недопустимый путь (<xref:System.IO.DirectoryNotFoundException> класса).  
  
-   Путь содержит только двоеточие «:» (<xref:System.NotSupportedException> класса).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем `Form1.vb` может вовсе не быть исходным файлом Visual Basic. Следует проверять все входные данные перед использованием их в приложении.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer>   
 [Практическое руководство: Загрузка звука асинхронно в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)   
 