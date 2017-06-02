---
title: "Практическое руководство. Воспроизведение системных звуков в Windows Forms | Microsoft Docs"
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
  - "звуки, воспроизведение для системных событий"
  - "воспроизведение звуков в Windows Forms"
  - "системные звуки, воспроизведение из Windows Forms"
  - "воспроизведение звуков системы"
  - "Класс SoundPlayer, системные звуки"
  - "воспроизведение звуков"
  - "примеры [Windows Forms] звуков"
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Воспроизведение системных звуков в Windows Forms
В следующем коде примера воспроизведения `Exclamation` системный звук во время выполнения. Дополнительные сведения о системных звуков, в разделе <xref:System.Media.SystemSounds>.  
  
## <a name="example"></a>Пример  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылку на <xref:System.Media?displayProperty=fullName> пространства имен.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>   
 [Практическое руководство: воспроизведение звукового сигнала в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)   
 [Практическое руководство: воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)