---
title: Практическое руководство. Воспроизведение системных звуков в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: b2ac6c4f2e3334a9b4c5ff4d2a6e31b6b9bf3673
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711242"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a>Практическое руководство. Воспроизведение системных звуков в Windows Forms
В следующем примере кода воспроизводится системный звук `Exclamation` во время выполнения. Дополнительные сведения о системных звуках см. в разделе <xref:System.Media.SystemSounds>.  
  
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
  
-   ссылка на пространство имен <xref:System.Media?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [Практическое руководство. Воспроизведение звукового сигнала в Windows Forms](how-to-play-a-beep-from-a-windows-form.md)
- [Практическое руководство. Воспроизведение звука в Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
