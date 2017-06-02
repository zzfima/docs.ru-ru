---
title: "Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms | Microsoft Docs"
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
  - "звуки, воспроизведение из ресурсов"
  - "воспроизведение звуков ресурсы [Windows Forms]"
  - "воспроизведение звуков из ресурсов"
  - "Класс SoundPlayer, воспроизведение звуков из ресурсов"
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms
Можно использовать <xref:System.Media.SoundPlayer> класса для воспроизведения звука из внедренного ресурса.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
 Импорт <xref:System.Media?displayProperty=fullName> пространства имен.  
  
 Включение звукового файла в качестве внедренного ресурса в проекте.  
  
 Замена»<>\>» с именем сборки, в который внедрен звуковой файл. Не включайте суффикс «.dll».  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer>   
 [Практическое руководство: воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [Практическое руководство: выполнение цикла воспроизводить звук в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)