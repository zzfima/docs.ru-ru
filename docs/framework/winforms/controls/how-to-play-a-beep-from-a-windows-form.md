---
title: Практическое руководство. Воспроизведение сигнала в Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: 1a72f88c05fb21c11864058ffbe81c1957525375
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966507"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Практическое руководство. Воспроизведение сигнала в Windows Forms
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
> Звук, воспроизводимый C# в образце кода, определяется <xref:System.Media.SystemSounds.Beep%2A> параметром системный звук. Дополнительные сведения см. в разделе <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для C#для этого примера требуется ссылка на <xref:System.Media?displayProperty=nameWithType> пространство имен.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [Практическое руководство. Воспроизводить системный звук из формы Windows](how-to-play-a-system-sound-from-a-windows-form.md)
- [Практическое руководство. Воспроизведение звука из формы Windows](how-to-play-a-sound-from-a-windows-form.md)
