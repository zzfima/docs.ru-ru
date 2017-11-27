---
title: "Практическое руководство. Подача звукового сигнала в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e214b368b65797100722cb41ad6a77ecd16424de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Практическое руководство. Подача звукового сигнала в Windows Forms
В этом примере воспроизводится звуковой сигнал во время выполнения.  
  
## <a name="example"></a>Пример  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  Звук, воспроизводимый в примере кода C#, определяется <xref:System.Media.SystemSounds.Beep%2A> звуковые настройки системы. Для получения дополнительной информации см. <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для C# в этом примере требуется ссылка на <xref:System.Media?displayProperty=nameWithType> пространства имен.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>  
 <xref:System.Media.SoundPlayer>  
 [Практическое руководство. Воспроизведение системных звуков в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 [Практическое руководство. Воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
